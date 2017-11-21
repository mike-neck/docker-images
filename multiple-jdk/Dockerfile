FROM alpine:3.6

ENV LANG C.UTF-8

ENV JAVA_HOME /usr/lib/jvm/openjdk-9
ENV JAVA9 /usr/lib/jvm/openjdk-9
ENV JAVA8 /usr/lib/jvm/openjdk-8
ENV PATH=${PATH}:/usr/lib/jvm/openjdk-9/bin/

RUN mkdir -p /usr/lib/jvm && \
  apk update && \
  apk upgrade && \
  apk add --no-cache curl && \
  curl -jksSLH "Cookie: oraclelicense=accept-securebackup-cookie" "http://download.java.net/java/jdk9-alpine/archive/181/binaries/jdk-9-ea+181_linux-x64-musl_bin.tar.gz" | tar xz -C /usr/lib/jvm && \
  ln -s /usr/lib/jvm/jdk-9 /usr/lib/jvm/openjdk-9 && \
  apk del curl

RUN apk add --no-cache openjdk8 && \
  ln -s /usr/lib/jvm/java-1.8/openjdk /usr/lib/jvm/openjdk-8

