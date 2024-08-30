FROM openjdk:21-slim-bookworm

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl=7.88.1-10+deb12u6 locales-all=2.36-9+deb12u7 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
ENV LANG ja_JP.UTF-8

ENV PAPER_URL="https://api.papermc.io/v2/projects/paper/versions/1.21.1/builds/41/downloads/paper-1.21.1-41.jar"

RUN mkdir /minecraft

WORKDIR /minecraft

RUN curl -o /papermc.jar -LO ${PAPER_URL} \
  && chmod +x /papermc.jar

ENTRYPOINT ["java", "-jar", "/papermc.jar"]
