
```java
public interface CustomerRepository extends JpaRepository<CustomerEntity, Integer> 
{


}

```

By extending `JpaRepository<CustomerEntity, Integer>`, the `CustomerRepository` interface inherits various CRUD methods such as `save`, `findById`, `findAll`, `delete`, etc., which can be used to perform database operations on `CustomerEntity` objects without the need for explicit implementation.
