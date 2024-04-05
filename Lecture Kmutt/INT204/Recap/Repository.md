```java
public interface EmployeeRepository extends JpaRepository<Employee,Integer> {  
}
```


```java
public interface CustomerRepository extends JpaRepository { public List findAllByCustomerNameContaining(String name); public List findAllByCityContainsOrderByCountry(String name); public List findAllByCreditLimitBetween(Double lower, Double upper); public List findAllByCustomerNameBetween(String lower, String upper); }
```




![](https://i.imgur.com/rcHk9ad.png)


![](https://i.imgur.com/Y7C6JAO.png)



### Native query
```java
@Query(value = "SELECT * FROM users WHERE email = ?1", nativeQuery = true)
User findByEmailNative(String email);

```