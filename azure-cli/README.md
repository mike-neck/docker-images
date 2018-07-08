azure-cli-dind
===

This image offers docker in docker with azure `az` command.
This is useful on OSX High-Sierra that has replaces openssl with libressl.
With this container you can upload a docker image to azure registry.

Usage
===

Mount docker socket and azure directory.

```
$ docker run --rm -it --privileged \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v ~/.azure:/root/.azure \
  mikeneck/azure-cli-dind
```
