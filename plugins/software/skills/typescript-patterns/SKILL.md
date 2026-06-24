---
name: typescript-patterns
description: Apply TypeScript strict-mode patterns including discriminated unions, branded types, const assertions, and framework-agnostic best practices. Use when writing TypeScript, reviewing TS code, or setting up TS tooling.
triggers:
  - typescript patterns
  - typescript best practices
  - ts strict
---

# TypeScript Patterns

Write TypeScript that uses the type system to prevent bugs at compile time, not just at runtime. These patterns are framework-agnostic.

## Strict Mode Essentials

Enable all strict checks in `tsconfig.json`:
```json
{
  "compilerOptions": {
    "strict": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true,
    "noFallthroughCasesInSwitch": true
  }
}
```

Rules:
- Never use `any`. Use `unknown` with type guards, or a specific type.
- Never use `@ts-ignore`. Use `@ts-expect-error` with a reason comment if truly unavoidable.
- Explicit return types on exported functions.
- Use `import type` for type-only imports.

## Discriminated Unions

Model variants with a shared literal field:
```typescript
type ApiResult<T> =
  | { status: 'success'; data: T }
  | { status: 'error'; error: string; code: number }
  | { status: 'loading' }

function handleResult(result: ApiResult<User>): void {
  switch (result.status) {
    case 'success':
      renderUser(result.data) // data is narrowed to User
      break
    case 'error':
      showError(result.error) // error and code are accessible
      break
    case 'loading':
      showSpinner()
      break
  }
}
```

Use exhaustive checks with `never`:
```typescript
default: {
  const _exhaustive: never = result
  throw new Error(`Unhandled status: ${_exhaustive}`)
}
```

## Branded Types

Prevent mixing semantically different values of the same base type:
```typescript
type UserId = string & { readonly __brand: 'UserId' }
type OrderId = string & { readonly __brand: 'OrderId' }

function createUserId(id: string): UserId {
  return id as UserId
}

function getUser(id: UserId): User { ... }
// getUser(orderId) — compile error
```

## Const Assertions

Lock literal types at declaration:
```typescript
const ROUTES = {
  home: '/',
  settings: '/settings',
  profile: '/profile',
} as const

type Route = typeof ROUTES[keyof typeof ROUTES]
// Route = '/' | '/settings' | '/profile'
```

## Utility Patterns

### Type-safe event emitters
```typescript
type Events = {
  'user:created': { user: User }
  'order:completed': { orderId: OrderId; total: number }
}

function emit<K extends keyof Events>(event: K, payload: Events[K]): void { ... }
```

## Error Handling

Use typed errors with Result pattern:
```typescript
type Result<T, E = Error> =
  | { ok: true; value: T }
  | { ok: false; error: E }

function parseConfig(raw: string): Result<Config, ParseError> {
  try {
    const parsed = JSON.parse(raw)
    return { ok: true, value: ConfigSchema.parse(parsed) }
  } catch (error) {
    return { ok: false, error: new ParseError('Invalid config', { cause: error }) }
  }
}
```

## Testing

- Use Vitest (Vite projects) or Jest
- Type-check test files — do not exclude them from tsconfig
- Test types themselves with `expectTypeOf` (Vitest) or `tsd`
- Mock with type safety: `vi.fn<Parameters<typeof fn>, ReturnType<typeof fn>>()`

## Tooling

- **Linter:** ESLint with `@typescript-eslint/recommended-type-checked`
- **Formatter:** Prettier or Biome
- **Bundler:** Vite, esbuild, or tsup for libraries
- **Package manager:** Use lockfile always. pnpm or npm.

## Do NOT
- Use `enum` — use const objects with `as const` and derived union types
- Use `namespace` — use ES modules
- Use `any` for "I'll type this later" — create a TODO type alias if needed: `type TODO_UserPayload = unknown`
- Use non-null assertion (`!`) — handle the null case or use a type guard
- Rely on type assertions (`as`) — narrow with control flow instead
