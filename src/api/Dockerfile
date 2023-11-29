FROM maven:3.8-openjdk-17 AS build
WORKDIR /app
COPY . . 
SHELL ["/bin/bash", "-c"]
RUN mvn clean package

FROM openjdk:17
WORKDIR /app
COPY --from=build /app/target/api-0.0.1-SNAPSHOT.jar ./api-0.0.1-SNAPSHOT.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","./api-0.0.1-SNAPSHOT.jar"]

