FROM java:8-jdk-alpine
LABEL maintainer www.boysec.cn
RUN  sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories && \
     apk add -U tzdata && \
     ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
COPY ./target/gateway-service.jar ./
EXPOSE 9999
CMD java -jar /gateway-service.jar
