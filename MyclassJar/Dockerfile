FROM maven:3.8.3-openjdk-17-slim AS builder
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn clean package

FROM openjdk:17
WORKDIR /app
COPY --from=builder /app/target/MyclassJar-1.0.jar /app/MyclassJar.jar
ENTRYPOINT ["java", "-jar", "MyclassJar.jar"]


