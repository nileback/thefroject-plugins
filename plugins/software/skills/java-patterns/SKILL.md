---
name: java-patterns
description: Apply modern Java (17+) patterns including records, sealed classes, pattern matching, virtual threads, and Spring Boot idioms. Use when writing Java, reviewing Java code, or modernizing legacy Java.
triggers:
  - java patterns
  - java best practices
  - spring patterns
---

# Java Patterns

Write modern Java (17+). Use new language features to reduce boilerplate and make code more expressive.

## Records (Java 16+)

Replace data classes with records:
```java
// Before: 40+ lines of getters, equals, hashCode, toString
public record User(String name, String email, Role role) {
    // Compact constructor for validation
    public User {
        Objects.requireNonNull(name, "name must not be null");
        Objects.requireNonNull(email, "email must not be null");
    }
}
```

Rules:
- Use records for immutable data carriers.
- Add validation in compact constructors.
- Records are final — they cannot be extended.
- Use records for DTOs, value objects, and configuration.

## Sealed Classes (Java 17+)

Model closed type hierarchies:
```java
public sealed interface Shape permits Circle, Rectangle, Triangle {
    double area();
}

public record Circle(double radius) implements Shape {
    public double area() { return Math.PI * radius * radius; }
}

public record Rectangle(double width, double height) implements Shape {
    public double area() { return width * height; }
}

public record Triangle(double base, double height) implements Shape {
    public double area() { return 0.5 * base * height; }
}
```

## Pattern Matching

### instanceof (Java 16+)
```java
if (shape instanceof Circle c) {
    return c.radius();
}
```

### Switch (Java 21+)
```java
return switch (shape) {
    case Circle c -> "Circle with radius " + c.radius();
    case Rectangle r -> "Rectangle " + r.width() + "x" + r.height();
    case Triangle t -> "Triangle with base " + t.base();
};
```

## Virtual Threads (Java 21+)

Use virtual threads for I/O-bound concurrent work:
```java
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    List<Future<Result>> futures = items.stream()
        .map(item -> executor.submit(() -> process(item)))
        .toList();

    List<Result> results = futures.stream()
        .map(f -> {
            try { return f.get(); }
            catch (Exception e) { throw new RuntimeException(e); }
        })
        .toList();
}
```

Rules:
- Use virtual threads for I/O operations (HTTP calls, database queries, file reads).
- Do not use virtual threads for CPU-bound work — use platform threads or ForkJoinPool.
- Virtual threads are cheap — create one per task, do not pool them.
- Avoid `synchronized` blocks with virtual threads — use `ReentrantLock` instead.

## Testing with JUnit 5

```java
@ExtendWith(MockitoExtension.class)
class UserServiceTest {
    @Mock UserRepository userRepository;
    @InjectMocks UserService userService;

    @Test
    void shouldReturnUserWhenExists() {
        var user = new User("1", "Ada", "ada@example.com");
        when(userRepository.findById("1")).thenReturn(Optional.of(user));

        var result = userService.findById("1");

        assertThat(result).isPresent();
        assertThat(result.get().name()).isEqualTo("Ada");
    }

    @ParameterizedTest
    @ValueSource(strings = {"", " ", "not-an-email"})
    void shouldRejectInvalidEmails(String email) {
        assertThrows(ValidationException.class, () -> userService.create("Name", email));
    }
}
```

## Build Tools

### Maven
- Use the Maven Wrapper (`mvnw`) for reproducible builds
- Manage dependency versions in `<dependencyManagement>`
- Use profiles for environment-specific builds

### Gradle
- Use Kotlin DSL (`build.gradle.kts`) for type-safe configuration
- Use version catalogs (`libs.versions.toml`) for dependency management

## Do NOT
- Use raw types (`List` instead of `List<String>`)
- Use `null` to represent absence — use `Optional<T>`
- Catch `Exception` broadly — catch specific exceptions
- Write getters/setters manually when a record would work
- Ignore compiler warnings — fix them or understand why they are safe
