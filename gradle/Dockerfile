FROM mikeneck/jdk8

RUN \
  groupadd -r build && \
  useradd -m -g build gradle

USER gradle
WORKDIR /home/gradle

RUN \
  curl -L https://services.gradle.org/distributions/gradle-2.8-all.zip -o gradle.zip

RUN \
  unzip -q gradle.zip -d tmp && \
  mkdir gradle && \
  mv tmp/gradle-2.8/bin gradle/ && \
  mv tmp/gradle-2.8/lib gradle/ && \
  mv tmp/gradle-2.8/init.d gradle/ && \
  rm -rf tmp && \
  rm gradle.zip

ENV GRADLE_HOME /home/gradle/gradle
ENV PATH=$PATH:$GRADLE_HOME/bin

CMD ["/bin/bash"]
