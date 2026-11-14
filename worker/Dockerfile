FROM maven:3.9.6-eclipse-temurin-21-alpine as builder

WORKDIR /usr/src/app

COPY . .

RUN mvn dependency:resolve

RUN mvn package

FROM eclipse-temurin:21-jre-alpine

COPY --from=builder /usr/src/app/target/worker-jar-with-dependencies.jar .

CMD ["java", "-jar", "worker-jar-with-dependencies.jar"]