For instance, let’s consider an e-commerce application. When displaying a list of products on a webpage, <mark style="background: #FFF3A3A6;">you may only need to transmit basic information</mark> like the product name, price, and image URL. In this scenario, instead of transferring the entire product object with all its associated data (e.g., reviews, descriptions, status), you can create a **ProductDTO** that includes only the essential fields for displaying the product list efficiently.
![[Pasted image 20240227212609.png]]

**Imagine you need to send a package across town.**

- **The Package:** The DTO is like your package. It holds everything you want to send together.
- **The Information:** This could be things like the address, name, and a list of what's inside. Each of these pieces of information is a data point within the DTO.
- **The Delivery Person:** Think of this as the way the DTO moves between different parts of your software system.

# **Why is this better than sending things separately?**

- **One Trip:** Instead of sending the address, then the name, then the list – you make one trip with everything together. This saves time and effort.
- **Easy to Understand:** The package has a clear label with the essential information, making it super simple to know what's inside.
![[Pasted image 20240227210649.png]]

simple DTO class
```java
@Getter  
@Setter  
public class SimpleEmployeeDTO {  
    private Integer id;  
    private String firstName;  
    private String lastName;  
    private String officePhone;  
  
  
}
```
- This class provide what  properties do you want to sent to user 



```java
@Configuration  
public class ApplicationConfig {  
    @Bean  
    public ModelMapper modelMapper(){  
        return  new ModelMapper();  
    }  
}
```
- Don t forgot config this !!! because if u not config this you cannot use @Autowired