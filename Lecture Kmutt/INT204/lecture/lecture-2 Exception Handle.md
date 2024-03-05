#lecture-2
[[07-INT204-Spring-Rest-Api-Exception-Handling.pdf]]

# JSON
- ERROR
- Normal
#status-code #error
# Status Code
- 200 <mark class="hltr-yellow">Normal</mark>
- 400 Client <mark class="hltr-red">Error</mark>
- 500 Server <mark class="hltr-red">Error</mark>
- 503 service not avalaible
- 401 Unauthorized
- 403 forbidden (Not authentication)
- 404 not found
return error information in <mark class="hltr-yellow">Body</mark>

# Standard Response 
![](https://i.imgur.com/LBbdJYx.png)

# @ResponseStatus
```java
@ResponseStatus(value = HttpStatus.NOT_FOUND) public class ItemNotFoundException extends RuntimeException { public ItemNotFoundException(String message) { super(message); }
```


# @ExceptionHandler
- Manager of exception
- Catch ของ service ทั้งหมด
```java
@ExceptionHandler(ItemNotFoundException.class)  
@ResponseStatus(HttpStatus.NOT_FOUND)  
public ItemNotFoundException handleItemNotFound(ItemNotFoundException exception){  
    return exception;  
}
```

![](https://i.imgur.com/0yXEqqe.png)

# @ControllerAdvice




let's compare `@ResponseStatus`, `@ExceptionHandler`, and `@ControllerAdvice` in the context of a Spring MVC application.

| Feature           | @ResponseStatus                                                    | @ExceptionHandler                                                                                                                    | @ControllerAdvice                                                                                                                                           |
| ----------------- | ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Purpose           | Sets the HTTP response status code directly on the handler method. | Handles exceptions thrown by controller methods within the same controller.                                                          | Global exception handler for all controllers in the application.                                                                                            |
| Scope             | Applies to individual handler methods within a controller.         | Applies to specific controller classes or globally to all controllers in the application.                                            | Applies globally across all controllers in the application.                                                                                                 |
| Usage             | Used within the handler method to set the response status code.    | Defined within a controller class to handle specific exceptions thrown by controller methods.                                        | Annotated class that contains methods to handle exceptions across multiple controllers.                                                                     |
| Example           | ```java @ResponseStatus(HttpStatus.NOT_FOUND)```                   | ```java @ExceptionHandler(ResourceNotFoundException.class)```                                                                        | ```java @ControllerAdvice```                                                                                                                                |
|                   | ```public String handleNotFound() { return "404"; }```             | ```public ResponseEntity<String> handleResourceNotFoundException(ResourceNotFoundException ex) { ... }```                            | ```public class GlobalExceptionHandler { @ExceptionHandler(Exception.class) public ResponseEntity<ErrorResponse> handleException(Exception ex) { ... } }``` |
| Flexibility       | Limited to setting the response status code only.                  | Provides more flexibility in handling exceptions, such as logging, custom error messages, and returning custom HTTP response bodies. | Offers the most flexibility as it can handle multiple exception types and provide centralized exception handling logic.                                     |
| Target Exceptions | Cannot handle exceptions thrown by controller methods directly.    | Handles exceptions thrown by controller methods specified in `@ExceptionHandler` annotations.                                        | Handles exceptions thrown by controller methods globally across all controllers.                                                                            |
| Configurability   | Limited to configuring HTTP response status codes.                 | Provides more configuration options for handling exceptions, such as specifying the response body, logging, etc.                     | Offers the most configuration options as it can handle multiple exception types and provide centralized configuration for exception handling.               |

In summary:

- `@ResponseStatus`: Sets the HTTP response status code directly on the handler method.
- `@ExceptionHandler`: Handles exceptions thrown by controller methods within the same controller.
- `@ControllerAdvice`: Acts as a global exception handler for all controllers in the application, offering the most flexibility and configurability.