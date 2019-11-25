# Scala and sbt Dockerfile

This repository contains **Dockerfile** of [Scala](http://www.scala-lang.org) and [sbt](http://www.scala-sbt.org).


## Base Docker Image ##

* [openjdk](https://hub.docker.com/_/openjdk)


## Installation ##

1. Install [Docker](https://www.docker.com)
2. Pull [automated build](https://hub.docker.com/r/doomoolmori/scala-sbt-for-ci/) from public [Docker Hub Registry](https://registry.hub.docker.com):
```
docker pull doomoolmori/scala-sbt-for-ci
```
Alternatively, you can build an image from Dockerfile:
(debian):
```
docker build \
  --build-arg BASE_IMAGE_TAG="8u212-b04-jdk-stretch" \
  --build-arg SBT_VERSION="1.3.4" \
  --build-arg SCALA_VERSION="2.13.1" \
  -t doomoolmori/scala-sbt-for-ci \
  github.com/doomoolmori/scala-sbt-for-ci.git#:debian
```
(oraclelinux7):
```
docker build \
  --build-arg BASE_IMAGE_TAG="11.0.2-jdk-oraclelinux7" \
  --build-arg SBT_VERSION="1.3.4" \
  --build-arg SCALA_VERSION="2.13.1" \
  -t doomoolmori/scala-sbt-for-ci \
  github.com/doomoolmori/scala-sbt-for-ci.git#:oracle
```

## Usage ##

```
docker run -it --rm doomoolmori/scala-sbt-for-ci
```

### Alternative commands ###
The container contains `bash`, `scala` and `sbt`.

```
docker run -it --rm doomoolmori/scala-sbt-for-ci scala
```

### Non-root ###
The container is prepared to be used with a non-root user called `sbtuser`

```
docker run -it --rm -u sbtuser -w /home/sbtuser doomoolmori/scala-sbt-for-ci
```

## Contribution policy ##

Contributions via GitHub pull requests are gladly accepted from their original author. Along with any pull requests, please state that the contribution is your original work and that you license the work to the project under the project's open source license. Whether or not you state this explicitly, by submitting any copyrighted material via pull request, email, or other means you agree to license the material under the project's open source license and warrant that you have the legal authority to do so.


## License ##

This code is open source software licensed under the [Apache 2.0 License]("http://www.apache.org/licenses/LICENSE-2.0.html").
