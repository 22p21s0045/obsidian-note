Optional is a new type introduced in Java 8. It is used to represent a value that may or may not be present. In other words, an Optional [object](https://www.developer.com/java/classes-objects-java/) can either contain a non-null value (in which case it is considered _present_) or it can contain no value at all (in which case it is considered _empty_).

**What is Optional?**

- A container that can hold either a value or nothing (empty).
- Used to represent situations where a value might not be present.
- Helps avoid `NullPointerException` errors.

**Creating Optional objects:**

- `Optional.of(value)`: Creates an `Optional` with a non-null value.
- `Optional.empty()`: Creates an empty `Optional`.
- `Optional.ofNullable(value)`: Creates an `Optional` that may be empty if the value is null.

**Using Optional objects:**

- `isPresent()`: Checks if the `Optional` contains a value.
- `get()`: Retrieves the value from a non-empty `Optional` (throws an exception if empty).
- `ifPresent(consumer)`: Executes a consumer function if the `Optional` has a value.
- `orElse(value)`: Returns the value if the `Optional` is empty, otherwise the provided default value.

**Pros and Cons:**

- **Pros:**
    - Prevents null pointer exceptions.
    - Provides safe ways to work with potentially missing values.
    - Easy to use as an ordinary class.
- **Cons:**
    - Can add overhead to code execution.
    - Some find it confusing to work with.