# Kubectl | EKS Support | Maycon Ritzmann

Minimal [Alpine Linux](https://alpinelinux.org/) image for running [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/).

## Build Image

### Build from git repository

```bash
$ git clone https://github.com/mayconritzmann/kubectl.git && cd kubectl
make build
```

The image will be tagged with the short hash from the latest git commit, e.g. `mayconritzmann/kubectl:d54e0e3`

### Pull from Docker Hub

```bash
docker pull mayconritzmann/kubectl:latest
```

Docker Hub images will be tagged as `mayconritzmann/kubectl:latest` and/or with git tags, e.g. `mayconritzmann/kubectl:v0.1`

## Run container

### Builtin test for `kubectl version`

```bash
$ docker run -it --rm \
    -v ${PWD}:/kubectl \
    mayconritzmann/kubectl \
    version
Client Version: version.Info{Major:"1", Minor:"18", GitVersion:"v1.18.12", GitCommit:"7cd5e9086de8ae25d6a1514d0c87bac67ca4a481", GitTreeState:"clean", BuildDate:"2020-11-12T09:18:55Z", GoVersion:"go1.13.15", Compiler:"gc", Platform:"linux/amd64"}
```

## Make

Makefile included for build, run, clean,...

```bash
$ make
build                          build container
build-no-cache                 build container without cache
clean                          remove images
help                           this help
history                        show docker history for container
inspect                        inspect container properties - pretty: 'make inspect | jq .' requires jq
logs                           show docker logs for container (ONLY possible while container is running)
run                            run container
```
