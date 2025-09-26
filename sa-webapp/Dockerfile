FROM maven:3.5-jdk-8 AS builder
WORKDIR /app
COPY pom.xml .
COPY src ./src
RUN mvn package

FROM openjdk:8-jdk-alpine
WORKDIR /app
COPY --from=builder /app/target/sentiment-analysis-web-0.0.1-SNAPSHOT.jar app.jar
ENTRYPOINT ["java", "-jar", "/app/app.jar"]
