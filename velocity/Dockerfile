FROM openjdk:17-slim-bullseye

RUN apt-get update && apt-get install -y curl locales-all
ENV LANG ja_JP.UTF-8

RUN mkdir /velocity

WORKDIR /velocity

RUN curl -o /velocity.jar -LO https://api.papermc.io/v2/projects/velocity/versions/3.3.0-SNAPSHOT/builds/416/downloads/velocity-3.3.0-SNAPSHOT-416.jar
RUN chmod +x /velocity.jar

ENTRYPOINT ["java", "-jar", "/velocity.jar"]
