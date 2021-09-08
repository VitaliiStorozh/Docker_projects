FROM alpine/git as clone
WORKDIR /app
RUN git clone -b dev https://github.com/ita-social-projects/GreenCity.git

FROM maven:3.6.3-jdk-11 as build
WORKDIR /app
COPY --from=clone /app/GreenCity /app
RUN mvn package

FROM openjdk:11-jre-slim
WORKDIR /app
COPY google-creds.json ./google-creds.json
COPY --from=build /app/core/target/*.jar /app
ENTRYPOINT ["sh", "-c"]
CMD ["java -jar *.jar"]
