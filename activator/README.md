mikeneck/activator
===

typesafe activator

How to run
===

```
$ docker run -v $HOME/.activator:/home/activator/.activator -v $HOME/.ivy2:/home/activator/.ivy2 -v $HOME/.sbt:/home/activator/.sbt -v /path/to/project:/home/activator/project mikeneck/activator
```

Base Image
===

[mikeneck/jdk8](https://hub.docker.com/r/mikeneck/jdk8/)

version
===

* 1.3.6, latest([1.3.6/Dockerfile](https://github.com/mike-neck/docker-images/blob/master/activator/Dockerfile))

Exposed port number
===

* 8888
* 9000

(exposed but it may be unable to access.)

User
===

activator

Working direstory
===

* `/home/activator`

Volume
===

* `/home/activator/.activator`
* `/home/activator/.ivy2`
* `/home/activator/.sbt`
* `/home/activator/project`
