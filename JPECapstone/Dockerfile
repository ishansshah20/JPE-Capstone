#FROM maven:3.6.0-jdk-11-slim AS build
#COPY src /home/app/src
#COPY pom.xml /home/app
#RUN mvn -f /home/app/pom.xml clean package
#
#FROM openjdk:15
#COPY --from=build /home/app/target/JPE-Capstone.jar /usr/local/lib/JPE-Capstone.jar
#ENTRYPOINT ["java", "-jar", "/usr/local/lib/JPE-Capstone.jar"]
#EXPOSE 8085

#-----------------------------------------------------------

#FROM maven:3.6.0-jdk-11-slim AS build
#WORKDIR /app
#COPY . .
#RUN mvn -f /app/pom.xml clean package
#
#FROM openjdk:15
#WORKDIR /app
#EXPOSE 80
#COPY --from=build /app/target/JPE-Capstone.jar .
#ENTRYPOINT ["java", "-jar", "JPE-Capstone.jar"]

#-------------------------------------
FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 80
ADD target/*.jar jpe-app.jar
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /jpe-app.jar" ]




