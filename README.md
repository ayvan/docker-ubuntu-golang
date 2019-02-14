## ayvan/ubuntu-golang

Originally forked from https://github.com/partlab/docker

Simple base docker image to run golang applications

### Usage

#### Build

```bash
$ docker build -t ayvan/ubuntu-golang
```

#### Download automated build

```bash
$ docker pull ayvan/ubuntu-golang
```

#### Usage

#### Using (example)

On Dockerfile

FROM ayvan/ubuntu-golang

ADD . /opt/go/src/myapp

RUN go get github.com/gin-gonic/gin
RUN go install myapp

ENTRYPOINT /opt/go/bin/myapp

EXPOSE 8080

```bash
$ docker build -t myapp .
$ docker run -p 8080:8080 --name myapp --rm myapp
```
