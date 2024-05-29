

- Show docker compose file
- Show Reverse proxy
- Explain monitoring / Github action


```
VM hostname : ip23tt1.sit.kmutt.ac.th
The sysadmin password : af7PAS999D
```


# Compose file

```yaml
version: '2.1'
services:
  database:
    build:
      context: ./database
      dockerfile: database.Dockerfile
    environment:
      - MYSQL_ROOT_PASSWORD=mysql@sit
    volumes:
      - ./database/mysql-lib:/var/lib/mysql
      - ./database/my.cnf:/etc/my.cnf
      - ./database/setup/db-script-v2.sql:/docker-entrypoint-initdb.d/db-script-v2.sql
    restart: on-failure
    networks:
    - test-networks
    healthcheck:
      test: ["CMD", "mysqladmin", "ping"]
      interval: 5s
      timeout: 5s
      retries: 5
  backend:
    depends_on:
      database:
          condition: service_healthy

      
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "8080:8080"
    environment:
      - MYSQL_USER=dev1
      - MYSQL_PASSWORD=dev@sit
      - MYSQL_URL=database
    networks:
      - test-networks
  frontend:
    image: title20306/frontend:latest
    ports:
      - 1449:1449
    networks:
    - default
  proxy:
    build: 
      context: ./proxy
      dockerfile: proxy.Dockerfile
    ports:
      - "80:80"
    restart: 
      always
    networks:
      - default
      - test-networks
    

networks:
  test-networks:
    driver: bridge
```


# Dockerfile Database

```Dockerfile
FROM mysql/mysql-server:latest
COPY ./my.cnf /etc/
VOLUME ./mysql-lib /var/lib/mysql
COPY ./setup/db-script-v2.sql /docker-entrypoint-initdb.d/
ENV  MYSQL_ROOT_PASSWORD=mysql@sit
ENV LANG=C.UTF-8
EXPOSE 3306
```


# Dockerfile Backend
```Dockerfile
FROM maven:3.8.3-openjdk-17
COPY . /backendAPI
WORKDIR /backendAPI
RUN mvn clean package
CMD java -jar $(find /backendAPI/target -name '*.jar')
EXPOSE 8080
```

# Config Proxy
```nginx
#From Edge network
server {
    listen 80;
    server_name intproj23.sit.kmutt.ac.th;

    location / {
        proxy_pass http://frontend:1449;

        
    } 
    

}

server {
    listen 8080;
    server_name intproj23.sit.kmutt.ac.th;
    location /v2/ {
        proxy_pass http://backend:8080;
    }
}


# From Kmutt Network

server {
    listen 80;
    server_name ip23tt1.sit.kmutt.ac.th;

    location / {
        rewrite ^/tt1/(.*)$ /$1 break;
        proxy_pass http://frontend:1449;

        
    } 
    

}

server {
    listen 8080;
    server_name ip23tt1.sit.kmutt.ac.th;
    location /v2/ {
        proxy_pass http://backend:8080;
    }
}
```