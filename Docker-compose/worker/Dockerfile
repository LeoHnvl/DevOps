FROM maven:3.5-jdk-8-alpine AS builder

WORKDIR /app

RUN mvn dependency:resolve && mvn package

FROM openjdk:8-jre-alpine

WORKDIR /app

COPY --from=builder /app/target /app

CMD [ "java", "-jar", "worker-jar-with-dependencies.jar"]