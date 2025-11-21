# 1️⃣ Use lightweight JDK
FROM openjdk:17-jdk-slim

# 2️⃣ Set working directory
WORKDIR /app

# 3️⃣ Copy the JAR file (generated after mvn package)
COPY target/*.jar app.jar

# 4️⃣ Expose backend port
EXPOSE 8080

# 5️⃣ Start the Spring Boot application
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
