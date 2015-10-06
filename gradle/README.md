mikeneck/gradle
===

Gradle with minimal spec.

### Using Java version

* jdk8u60

### Base image

* [mikeneck/jdk8](https://hub.docker.com/r/mikeneck/jdk8/)

### Gradle versions

* Latest
  * Gradle 2.7
* mikeneck/gradle:2.7
  * Gradle 2.7

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
