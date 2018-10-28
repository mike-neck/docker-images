FROM python:3.7-alpine3.8

RUN \
  apk update && \
  apk add groff less && \
  mkdir /project && \
  pip install awscli --upgrade

VOLUME /project
WORKDIR /project

