FROM openjdk:17.0.2-slim-bullseye@sha256:aaa3b3cb27e3e520b8f116863d0580c438ed55ecfa0bc126b41f68c3f62f9774

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl=7.88.1-10+deb12u8 locales-all=2.36-9+deb12u9 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
ENV LANG ja_JP.UTF-8

RUN mkdir /data
WORKDIR /data

ENV VELOCITY_URL="https://api.papermc.io/v2/projects/velocity/versions/3.4.0-SNAPSHOT/builds/453/downloads/velocity-3.4.0-SNAPSHOT-453.jar"

RUN curl -o /velocity.jar -LO ${VELOCITY_URL} \
  && chmod +x /velocity.jar

ENTRYPOINT ["java", "-jar", "/velocity.jar"]
