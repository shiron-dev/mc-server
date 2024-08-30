FROM openjdk:17.0.2-slim-bullseye

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl=7.88.1-10+deb12u6 locales-all=2.36-9+deb12u7 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*
ENV LANG ja_JP.UTF-8

RUN mkdir /velocity

WORKDIR /velocity

RUN curl -o /velocity.jar -LO https://api.papermc.io/v2/projects/velocity/versions/3.3.0-SNAPSHOT/builds/416/downloads/velocity-3.3.0-SNAPSHOT-416.jar \
  && chmod +x /velocity.jar

ENTRYPOINT ["java", "-jar", "/velocity.jar"]
