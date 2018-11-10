FROM python:3.7-alpine3.8

RUN \
  apk update && \
  apk add groff less build-base && \
  mkdir /project && \
  pip install awscli aws-sam-cli --upgrade && \
  apk del build-base

VOLUME /project
WORKDIR /project

