3/8/2024
[[2023-INT210-07 Integrating Frontend and Backend.pdf]]

#tips 
backend API = resource server
#review
## Review 
- install Nodejs
- create project
- install dependency
![](https://i.imgur.com/ITtkqgt.png)
- Fetch API run from browser

## Step
5. Run project with Maven (./mvnw spring-boot:run) 
6. Build .jar file (./mvnw clean package) 
7. Run .jar file (java –jar target/*.jar)
#problem 
## Cross origin problem
- Check domain and port

![](https://i.imgur.com/rWrGzxg.png)


```js Origin
http://lvm65089.sit.kmutt.ac.th:3000


```


## Database password
```
dwZxK@tqK7
```
## Login

```js Login to MySQL
sudo mysql -u root -p
```

## Set Environment
![](https://i.imgur.com/TC2zUDk.png)


Library I must create authUtils.js
- getuserByID(id) : fetchapi return objectuser
- getTokenById(id): return token
- updateToken(id,updateData): if field not provide not do anything
- createToken(id) : POST to create token  return void || create id,token,expireAt
- createUser(userData:object) userdata:{username,email,passoword}
- extendTokenDuration(id) : now + 7 วัน and updateToken
- UI log in