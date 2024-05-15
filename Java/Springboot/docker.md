# Dockerfile for Springboot 

```dockerfile
FROM openjdk

WORKDIR /app

# Copy maven executable to work directory
COPY ./mvnw .
COPY ./.mvn .mvn

RUN chmod +x ./mvnw

# Copy the pom.xml and download dependencies
COPY ./pom.xml .

# Copy over the project source 
COPY ./src ./src

# Expose port 8080 for the app
EXPOSE 8080

# run the application
ENTRYPOINT  ./mvnw spring-boot:run     
```

This runs the spring boot app in a containter
