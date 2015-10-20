FROM mikeneck/jdk8

RUN \
  groupadd -r repo && \
  useradd -m -g repo gitbucket && \
  mkdir /home/gitbucket/bin && \
  curl -L \
    https://github.com/gitbucket/gitbucket/releases/download/3.7/gitbucket.war \
    -o /home/gitbucket/bin/gitbucket.war && \
  mkdir /home/gitbucket/.gitbucket

VOLUME /home/gitbucket/.gitbucket

RUN \
  chown -R gitbucket /home/gitbucket && \
  chown gitbucket /home/gitbucket/.gitbucket && \
  chown gitbucket /home/gitbucket/bin/gitbucket.war

EXPOSE 8080
EXPOSE 29418

USER gitbucket
WORKDIR /home/gitbucket

ENTRYPOINT ["java", "-jar", "bin/gitbucket.war"]
