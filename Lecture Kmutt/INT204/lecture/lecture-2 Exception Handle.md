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
```java
@ExceptionHandler(ItemNotFoundException.class)  
@ResponseStatus(HttpStatus.NOT_FOUND)  
public ItemNotFoundException handleItemNotFound(ItemNotFoundException exception){  
    return exception;  
}
```