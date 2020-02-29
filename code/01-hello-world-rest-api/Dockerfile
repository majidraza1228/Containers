FROM openjdk:8-jdk-alpine
VOLUME /tmp
EXPOSE 3100
ADD target/*.jar app.jar
ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Dserver.port=3100 -Djava.security.egd=file:/dev/./urandom -jar /app.jar" ]