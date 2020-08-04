FROM openjdk:8-alpine3.9
VOLUME [ "/tmp" ]

RUN apk add --no-cache tzdata
ENV TZ America/Sao_Paulo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

COPY target/*.jar app.jar

EXPOSE 80

ENTRYPOINT ["sh", "-c", "exec java -XX:+UnlockExperimentalVMOptions -XX:+UseCGroupMemoryLimitForHeap  -Djava.security.egd=file:/dev/./urandom -jar app.jar -Dfile.encoding=UTF-8"]