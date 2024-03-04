# Development
## Build

```shell
DOCKER_BUILDKIT=1
docker build . -t 'infra-case-hello:local'
```

## Run

```shell
docker run -p 8080:8080 --volume /tmp/nginx:/tmp/nginx infra-case-hello:local
```