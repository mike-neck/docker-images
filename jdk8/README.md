mikeneck/jdk8
===

Jdk8 image with minimal spec

### Base image

* [ubuntu:15.10](https://hub.docker.com/_/ubuntu-debootstrap/)

### installed packages

* `software-properties-common`
* `oracle-java8-installer`
* `zip`
* `unzip`
* `curl`

### added cert files

* cert of startssl
  * root - level4
