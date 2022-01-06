#FROM maven:3.6.0-jdk-11-slim AS build
#WORKDIR /app
#COPY . .
#RUN mvn -f /app/pom.xml clean package
#
#FROM openjdk:15
#WORKDIR /app
#EXPOSE 80
#COPY --from=build /app/target/jpe-app.jar .
#ENTRYPOINT ["java", "-jar", "jpe-app.jar"]

#-------------------------------------
#FROM openjdk:8-jdk-alpine
#VOLUME /tmp
#EXPOSE 80
#ADD target/*.jar JPECapstone.jar
#ENV JAVA_OPTS=""
#ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /JPECapstone.jar" ]

#-------------------------------------
FROM maven:3.6.1-jdk-8-slim AS build
RUN mkdir -p /workspace
WORKDIR /workspace
COPY pom.xml /workspace
COPY src /workspace/src
RUN mvn -f pom.xml clean package

FROM openjdk:8-alpine
COPY --from=build /workspace/target/*.jar jpe-app.jar
EXPOSE 80
ENTRYPOINT ["java","-jar","jpe-app.jar"]






