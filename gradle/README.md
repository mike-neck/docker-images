mikeneck/gradle
===

Gradle with minimal spec.

### Using Java version

* jdk8u60

### Base image

* [mikeneck/jdk8](https://hub.docker.com/r/mikeneck/jdk8/)

### Gradle versions

* 2.9, latest ([2.9/Dockerfile](https://github.com/mike-neck/docker-images/blob/master/gradle/Dockerfile))
* 2.8 ([2.8/Dockerfile](https://github.com/mike-neck/docker-images/blob/5273d90efc8568b3806a82f0a57785d4b5116593/gradle/Dockerfile))
* 2.7 ([2.7/Dockerfile](https://github.com/mike-neck/docker-images/blob/bd3c0498b6f3b5a8e5e15e3897b6832ad8d39dcb/gradle/Dockerfile))

### Usage

To launch this image.

```sh
docker run mikeneck/gradle
```

##### Launch with Volumes

If you want to build your project with this image, launch this image with `-v` option.

```sh
docker run -v /home/you/.gradle:/home/gradle/.gradle -v /home/you/path/to/project:/home/gradle/project mikeneck/gradle
```

There are two volumable directories.

`VOLUME`|purpose
:--|:--
`/home/gradle/.gradle`|To share dependency caches
`/home/gradle/project`|To mount your project

### Environmental value

* `GRADLE_HOME`
  * `/home/gradle/gradle`
* `PATH`
  * `$PATH:$GRADLE_HOME/bin`
