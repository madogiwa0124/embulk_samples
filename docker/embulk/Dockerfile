FROM openjdk:8-jre-alpine

RUN wget -q https://dl.embulk.org/embulk-latest.jar -O /bin/embulk \
  && chmod +x /bin/embulk

RUN apk add --no-cache libc6-compat
RUN embulk gem install embulk-input-mysql
RUN embulk gem install embulk-input-postgresql
RUN embulk gem install embulk-output-mysql
RUN embulk gem install embulk-output-postgresql

WORKDIR /work

ENTRYPOINT ["java", "-jar", "/bin/embulk"]
