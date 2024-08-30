FROM openjdk:21-slim-bookworm

RUN apt-get update && apt-get install -y curl locales-all
ENV LANG ja_JP.UTF-8

RUN mkdir /minecraft

WORKDIR /minecraft

RUN curl -o /papermc.jar -LO https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/41/downloads/paper-1.21.1-41.jar
RUN chmod +x /papermc.jar

ENTRYPOINT ["java", "-jar", "/papermc.jar"]
