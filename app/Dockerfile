# Base Image
FROM eclipse-temurin:21-jre

# Working Directory
WORKDIR /app

# Copy JAR File
COPY target/*.jar app.jar

# Application Port
EXPOSE 8080

# Run Application
ENTRYPOINT ["java","-jar","app.jar"]