FROM docker:18.03.1-dind

RUN mkdir /root/.azure /azure-cli
VOLUME /root/.azure
WORKDIR /azure-cli

RUN \
  apk add --no-cache curl libffi python3-dev bash openssh ca-certificates jq openssl && \
  apk add --no-cache --virtual .build-deps gcc make openssl-dev libffi-dev musl-dev && \
  update-ca-certificates && \
  ln -s /usr/bin/python3.6 /usr/bin/python && \
  ln -s /usr/bin/pip3 /usr/bin/pip && \
  pip install --no-cache-dir --upgrade jmespath-terminal && \
  curl -L https://aka.ms/InstallAzureCli | \
    sed -e "s/tmp_XXXX/tmp_XXXXXX/g" \
      -e "s/\/dev\/tty/config.txt/g" > install.sh && \
  chmod +x install.sh && \
  echo /azure-cli/lib >> config.txt && \
  echo /azure-cli/bin >> config.txt && \
  echo y >> config.txt && \
  ./install.sh && \
  cat /azure-cli/lib/az.completion > ~/.bashrc && \
  runDeps="$( \
    scanelf --needed --nobanner --recursive /usr/local \
        | awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' \
        | sort -u \
        | xargs -r apk info --installed \
        | sort -u \
    )"  && \  
  apk add --virtual .rundeps $runDeps && \
  apk del .build-deps

WORKDIR /
ENV PATH $PATH:/azure-cli/bin

CMD bash
