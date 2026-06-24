---
name: go-patterns
description: Apply Go idioms including error handling patterns, goroutines and channels, interface design, embedding, and project layout. Use when writing Go, reviewing Go code, or setting up Go projects.
triggers:
  - go patterns
  - golang best practices
  - go idioms
---

# Go Patterns

Write idiomatic Go. The language has strong opinions — follow them rather than importing patterns from other languages.

## Error Handling

### The Fundamental Pattern
```go
result, err := doSomething()
if err != nil {
    return fmt.Errorf("doSomething failed: %w", err)
}
```

Rules:
- Always handle errors immediately after the call. Never defer error checking.
- Wrap errors with context using `fmt.Errorf("context: %w", err)`.
- Use `errors.Is()` and `errors.As()` for error inspection, not type assertions.
- Define sentinel errors for expected conditions: `var ErrNotFound = errors.New("not found")`.
- Return errors — do not panic for expected failures.

### Custom Error Types
```go
type ValidationError struct {
    Field   string
    Message string
}

func (e *ValidationError) Error() string {
    return fmt.Sprintf("validation failed on %s: %s", e.Field, e.Message)
}
```

## Concurrency

Use `errgroup` for parallel work — it wraps the manual goroutine + WaitGroup + channel pattern into a clean API with built-in error propagation and context cancellation:
```go
g, ctx := errgroup.WithContext(ctx)
for _, item := range items {
    g.Go(func() error {
        return process(ctx, item)
    })
}
if err := g.Wait(); err != nil {
    return err
}
```

Rules:
- Always pass `context.Context` as the first parameter for cancellable operations.
- Use `select` with `ctx.Done()` to make operations cancellable.
- Never start goroutines that cannot be stopped.
- Buffer channels when the count is known to prevent goroutine leaks.

## Interfaces

Design small, focused interfaces:
```go
type Reader interface {
    Read(p []byte) (n int, err error)
}

type Storer interface {
    Get(ctx context.Context, id string) (Item, error)
    Put(ctx context.Context, item Item) error
}
```

Rules:
- Define interfaces where they are used, not where they are implemented.
- Keep interfaces small (1-3 methods). Compose larger behaviors from small interfaces.
- Accept interfaces, return structs.
- Name single-method interfaces after the method with an "-er" suffix: `Reader`, `Writer`, `Closer`.

## Project Layout

```
cmd/
  myapp/
    main.go          # entry point
internal/
  server/            # HTTP handlers
  store/             # data access
  domain/            # business logic (no external dependencies)
pkg/                 # public library code (if needed)
```

- Use `internal/` for code that should not be imported by other projects.
- Keep `main.go` minimal — parse config, wire dependencies, start server.
- Business logic in `internal/domain/` should have zero infrastructure imports.

## Testing

### Table-Driven Tests
```go
func TestParseAmount(t *testing.T) {
    tests := []struct {
        name    string
        input   string
        want    int
        wantErr bool
    }{
        {"valid integer", "42", 42, false},
        {"negative", "-1", -1, false},
        {"empty string", "", 0, true},
        {"not a number", "abc", 0, true},
    }
    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            got, err := ParseAmount(tt.input)
            if (err != nil) != tt.wantErr {
                t.Errorf("ParseAmount(%q) error = %v, wantErr %v", tt.input, err, tt.wantErr)
                return
            }
            if got != tt.want {
                t.Errorf("ParseAmount(%q) = %d, want %d", tt.input, got, tt.want)
            }
        })
    }
}
```

## Tooling

- **Formatter:** `gofmt` (non-negotiable — always format)
- **Linter:** `golangci-lint` with default config as a starting point
- **Vet:** `go vet ./...` — catches common mistakes
- **Test:** `go test -race ./...` — always use the race detector

## Do NOT
- Use `init()` functions — they make code harder to test and reason about
- Use package-level mutable state — pass dependencies explicitly
- Ignore errors with `_ = doSomething()` — handle or explicitly document why it is safe
- Use naked returns — always name what you are returning in the return statement
- Import packages only for side effects without a comment explaining why
