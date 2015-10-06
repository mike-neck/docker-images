FROM ubuntu-debootstrap:15.10

RUN \
  apt-get update && \
  apt-get install -y software-properties-common && \
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections

RUN \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y \
    oracle-java8-installer \
    zip \
    curl \
    unzip && \
  apt-get clean && \
  rm -rf /var/cache/oracle-jdk8-installer

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

RUN \
  curl -LO http://www.startssl.com/certs/ca.crt && \
  curl -LO http://www.startssl.com/certs/sub.class1.server.ca.crt && \
  curl -LO http://www.startssl.com/certs/sub.class2.server.ca.crt && \
  curl -LO http://www.startssl.com/certs/sub.class3.server.ca.crt && \
  curl -LO http://www.startssl.com/certs/sub.class4.server.ca.crt

RUN \
  keytool -import -trustcacerts -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt -alias startcom.ca -file ca.crt && \
  keytool -import -trustcacerts -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt -alias startcom.ca.sub.class1 -file sub.class1.server.ca.crt && \
  keytool -import -trustcacerts -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt -alias startcom.ca.sub.class2 -file sub.class2.server.ca.crt && \
  keytool -import -trustcacerts -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt -alias startcom.ca.sub.class3 -file sub.class3.server.ca.crt && \
  keytool -import -trustcacerts -keystore $JAVA_HOME/jre/lib/security/cacerts -storepass changeit -noprompt -alias startcom.ca.sub.class4 -file sub.class4.server.ca.crt

RUN \
  rm -f ca.crt sub.class1.server.ca.crt sub.class2.server.ca.crt sub.class3.server.ca.crt sub.class4.server.ca.crt

CMD ["/bin/bash"]
