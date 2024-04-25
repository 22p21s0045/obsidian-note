Compose v1

```yaml
version: '2.1'
services:
  mysqldb:
    build:
      context: ./database
      dockerfile: database.Dockerfile
    healthcheck:
      test: ["CMD", "mysqladmin" ,"ping", "-h", "localhost"]
      interval: 5s
      timeout: 10s
      retries: 10
    networks:
      - devNetwork

  springapp:
    build:
      context: .
      dockerfile: Dockerfile
    depends_on:
      mysqldb:  # Notice the indentation here
        condition: service_healthy
    networks:
      - devNetwork
    environment:
      - MYSQL_URL=jdbc:mysql://mysqldb:3306/task_base?serverTimezone=UTC
      - MYSQL_USER=root
      - MYSQL_PASSWORD=mysql@sit

networks:
  devNetwork:
    driver: bridge
```