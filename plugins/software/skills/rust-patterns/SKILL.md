---
name: rust-patterns
description: Apply Rust idioms for ownership, borrowing, error handling with Result/Option, trait patterns, testing, and cargo tooling. Use when writing Rust, reviewing Rust code, or setting up Rust projects.
triggers:
  - rust patterns
  - rust best practices
  - rust idioms
---

# Rust Patterns

Write idiomatic Rust. Leverage the type system and ownership model to eliminate bugs at compile time.

## Ownership and Borrowing

- Each value has exactly one owner.
- Borrow immutably (`&T`) as many times as needed, or mutably (`&mut T`) exactly once.
- References must always be valid — no dangling pointers.

### Common Patterns
```rust
// Take ownership when you need to store or transform the value
fn process(data: Vec<u8>) -> Result<Output, Error> { ... }

// Borrow when you only need to read
fn analyze(data: &[u8]) -> Summary { ... }

// Borrow mutably when you need to modify in place
fn normalize(data: &mut Vec<f64>) { ... }
```

### Lifetime Annotations
Only add lifetimes when the compiler asks. Start without them:
```rust
// Let the compiler infer when possible
fn first_word(s: &str) -> &str { ... }

// Add lifetimes when the compiler cannot infer the relationship
fn longest<'a>(a: &'a str, b: &'a str) -> &'a str { ... }
```

## Error Handling

### Use Result and Option Everywhere
```rust
fn parse_config(path: &Path) -> Result<Config, ConfigError> {
    let content = fs::read_to_string(path)
        .map_err(|e| ConfigError::ReadFailed { path: path.to_owned(), source: e })?;
    let config: Config = toml::from_str(&content)
        .map_err(|e| ConfigError::ParseFailed { source: e })?;
    Ok(config)
}
```

### Error Libraries
Use `thiserror` for library errors (structured, specific) and `anyhow` for application errors (quick, context-rich):
```rust
// Library: define specific error types with thiserror
#[derive(Debug, thiserror::Error)]
enum ConfigError {
    #[error("failed to read {path}")]
    ReadFailed { path: PathBuf, source: std::io::Error },
    #[error("failed to parse config")]
    ParseFailed { source: toml::de::Error },
}

// Application: use anyhow for ergonomic error propagation with context
let config = parse_config("config.toml")
    .context("failed to load application config")?;
```

### The ? Operator
- Use `?` for early returns on error — do not match on every Result.
- Chain `.context()` or `.map_err()` to add context before `?`.

## Trait Patterns

### Define Small Traits
```rust
trait Store {
    fn get(&self, id: &str) -> Result<Item, StoreError>;
    fn put(&self, item: &Item) -> Result<(), StoreError>;
}
```

Implement traits on in-memory structs for testing. Use `impl Trait` for return types when callers do not need to name the concrete type.

## Common Idioms

### Builder Pattern
```rust
let config = ConfigBuilder::new()
    .port(8080)
    .host("0.0.0.0")
    .max_connections(100)
    .build()?;
```

### Newtype Pattern
```rust
struct UserId(String);
struct Email(String);
// Prevents accidentally passing an Email where a UserId is expected
```

## Testing

```rust
#[cfg(test)]
mod tests {
    use super::*;

    #[test]
    fn parse_valid_config() {
        let input = r#"port = 8080"#;
        let config = parse_config_str(input).unwrap();
        assert_eq!(config.port, 8080);
    }

    #[test]
    fn parse_invalid_config_returns_error() {
        let input = "not valid toml {{{{";
        assert!(parse_config_str(input).is_err());
    }
}
```

- Place tests in a `mod tests` block inside the same file.
- Use integration tests in `tests/` for cross-module behavior.
- Use `#[should_panic]` sparingly — prefer testing the Result variant.

## Tooling

- **Formatter:** `cargo fmt` — always format, non-negotiable
- **Linter:** `cargo clippy` — treat warnings as errors in CI
- **Test:** `cargo test` — run on every change
- **Check:** `cargo check` — fast type-check without building
- **Audit:** `cargo audit` — check dependencies for known vulnerabilities

## Do NOT
- Use `unwrap()` in production code — use `?` or `expect("reason")`
- Use `clone()` to satisfy the borrow checker without understanding why — fix the ownership
- Ignore clippy warnings — fix them or explicitly allow with a reason: `#[allow(clippy::..., reason = "...")]`
- Use `unsafe` without a safety comment explaining the invariants
- Fight the borrow checker — if it is hard to express, the design may need rethinking
