FROM openjdk:17.0.2-slim-bullseye

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl=7.74.0-1.3+deb11u12 locales-all=2.31-13+deb11u10 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
ENV LANG ja_JP.UTF-8

RUN mkdir /data
WORKDIR /data

ENV VELOCITY_URL="https://api.papermc.io/v2/projects/velocity/versions/3.4.0-SNAPSHOT/builds/453/downloads/velocity-3.4.0-SNAPSHOT-453.jar"

RUN curl -o /velocity.jar -LO ${VELOCITY_URL} \
  && chmod +x /velocity.jar

ENTRYPOINT ["java", "-jar", "/velocity.jar"]
