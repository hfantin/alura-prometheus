#FROM openjdk:8-jdk-alpine
FROM adoptopenjdk/openjdk8:jdk8u372-b07-alpine-slim

RUN addgroup -S spring && adduser -S spring -G spring

USER spring:spring

ARG JAR_FILE=target/*jar
COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","-Xms128M","-Xmx128M","-XX:PermSize=64m","-XX:MaxPermSize=128m","-Dspring.profiles.active=prod","-jar","/app.jar"]
