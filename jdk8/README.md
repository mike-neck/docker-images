mikeneck/jdk8
===

Jdk8 image with minimal spec

### Base image

* [ubuntu:15.10](https://hub.docker.com/_/ubuntu-debootstrap/)

### versions

* jdk1.8.60, latest ([1.8/Dockerfile](https://github.com/mike-neck/docker-images/blob/9d456378b0680b441941c146ae01d23fcc4a5c61/jdk8/Dockerfile))

### installed packages

* `software-properties-common`
* `oracle-java8-installer`
* `zip`
* `unzip`
* `curl`

### added cert files

* cert of startssl
  * root - level4
