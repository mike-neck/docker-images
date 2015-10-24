FROM mikeneck/jdk8

RUN \
  groupadd -r dev && \
  useradd -m -g dev activator && \
  mkdir /home/activator/.activator && \
  mkdir /home/activator/.sbt/ && \
  mkdir /home/activator/.ivy2/ && \
  mkdir /home/activator/project

RUN \
  curl -L \
    https://downloads.typesafe.com/typesafe-activator/1.3.6/typesafe-activator-1.3.6.zip \
    -o activator.zip && \
  unzip -q activator.zip -d tmp && \
  mv tmp/activator-dist-1.3.6/ /home/activator/bin && \
  rm activator.zip

ENV PATH=$PATH:/home/activator/bin

VOLUME /home/activator/.activator
VOLUME /home/activator/.sbt
VOLUME /home/activator/.ivy2
VOLUME /home/activator/project

RUN \
  chown -R activator /home/activator/.activator && \
  chown -R activator /home/activator/.sbt && \
  chown -R activator /home/activator/.ivy2 && \
  chown -R activator /home/activator/project && \
  chown -R activator /home/activator/bin

USER activator
WORKDIR /home/activator

EXPOSE 8888
EXPOSE 9000

CMD ["/bin/bash"]
