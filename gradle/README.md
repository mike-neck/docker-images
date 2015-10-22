mikeneck/gradle
===

Gradle with minimal spec.

### Using Java version

* jdk8u60

### Base image

* [mikeneck/jdk8](https://hub.docker.com/r/mikeneck/jdk8/)

### Gradle versions

* 2.8, latest ([2.8/Dockerfile](https://github.com/mike-neck/docker-images/blob/5273d90efc8568b3806a82f0a57785d4b5116593/gradle/Dockerfile))
* 2.7 ([2.7/Dockerfile](https://github.com/mike-neck/docker-images/blob/bd3c0498b6f3b5a8e5e15e3897b6832ad8d39dcb/gradle/Dockerfile))

### User/Group

* group
  * build
* user
  * gradle

### Environmental value

* `GRADLE_HOME`
  * `/home/gradle/gradle`
* `PATH`
  * `$PATH:$GRADLE_HOME/bin`
