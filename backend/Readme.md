# Spring Boot Backend Deployment Guide 

## Prerequisites

- Java Development Kit (JDK 17 or higher) installed.
- Maven installed.
- Spring Boot application source code or JAR file.

## Step 1: Install Java

1. Verify if Java is installed by running the following command:

   ```bash
   java -version
   ```

If Java is not installed, install the JDK from OpenJDK.

```shell
apt update && apt install openjdk-17-jdk -y
java -version
```

## Step 2: Install Maven

Installing maven in ubuntu:

```shell
apt install maven -y
```

### Verify Maven installation:

```bash

mvn -version
```

## Step 3: Build the Spring Boot Application

### Update DB credentials in application.properties:

```shell
vim backend/src/main/resources/application.properties

   server.port=8080
   spring.datasource.url=jdbc:mariadb://<DB_HOST>:3306/<DB_NAME>
   spring.datasource.username=<DB_USER>
   spring.datasource.password=<DB_PASS>
```

### Build springboot Application using maven

```shell
mvn clean package
```

## Step 4: Run the Application

Run the generated JAR file by using the following command:

```bash

java -jar target\spring-backend-v1.jar
```

The application will start and be accessible at:

http://localhost:8080

### Step 5: Keep the Application Running


To keep the application running in the background, you can use nohup or a similar method. 

```
nohup java -jar student-registration-backend-0.0.1-SNAPSHOT.jar > app.log 2>&1 &
```
