#repositor
### CustomerRepositroy
```java
public interface CustomerRepository extends JpaRepository<Customer,Integer> {
}
```


### EmployeeRepository

```java
public interface EmployeeRepository extends JpaRepository<Employee, Integer> {
}
```


### OfficeRepository
```java
public interface OfficeRepository extends JpaRepository<Office, String> {
}
```

### ProductRepository

```java
public interface ProductRepository extends JpaRepository<Product, String> {
}
```