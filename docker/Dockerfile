# ==================== Build Stage ====================
FROM maven:3.9.9-eclipse-temurin-17 AS build
WORKDIR /app

# Copy pom and download dependencies first (cache optimization)
COPY app/sample-spring-boot-app/pom.xml .
RUN mvn dependency:go-offline -B

# Copy source and build
COPY app/sample-spring-boot-app/src ./src
RUN mvn clean package -DskipTests

# ==================== Runtime Stage ====================
FROM eclipse-temurin:17-jre-alpine
WORKDIR /app

COPY --from=build /app/target/sample-spring-boot-app-0.0.1-SNAPSHOT.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
