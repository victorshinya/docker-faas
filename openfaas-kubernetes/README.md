# OpenFaas Functions Docker and Kubernetes

## Pre-requisites

- Download and install [Docker](https://docker.com) and create an account.
- Pull the most recent OpenFaaS images.

```sh
curl -sSL https://raw.githubusercontent.com/openfaas/faas/master/docker-compose.yml | grep image | awk -F " " '{print $NF}' | xargs -L1 docker pull
```

- Setup a single-node cluster.

```sh
docker swarm init
```

- Create an account on [Docker Hub](https://hub.docker.com/) and log in.

```sh
docker login
```

- Download and install [OpenFaaS CLI](https://openfaas.com).
```sh
curl -sL cli.openfaas.com | sudo sh
```

## How-to

Build ImageMagick function. The `-yaml` flag is used to reference your build on a yml file.

```sh
faas-cli build -yaml image.yml
```

Deploy ImageMagick function into [OpenFaaS UI](http://127.0.0.1:8080).

```sh
faas-cli deploy -yaml image.yml
```

Send the `whale.jpg` image as a parameter to **resizer** function (our ImageMagick function) and execute.

```sh
cat whale.jpg | faas-cli invoke resizer > whale-smaller.jpg
```

Check out `whale-smaller.jpg` image. You can change the resize reference.
