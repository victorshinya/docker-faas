[![](https://img.shields.io/badge/IBM%20Cloud-powered-blue.svg)](https://cloud.ibm.com)
[![Platform](https://img.shields.io/badge/platform-docker-blue.svg?style=flat)](https://developer.ibm.com/docker/)

# Build Functions using Docker

Develop and deploy new serverless applications are quite simple. Break your solution into several separate components, and then, break it again into several functions (or actions). However, there are quite a few features that require to use other programming languages or even using opensource services (such as ImageMagick), and your serverless platform does not have a native support. In this case, you need to use a Docker container to build your function.

Learn how to use Apache OpenWhisk and OpenFaaS using Docker, Docker Swarm, and Kubernetes.

## Setup your local environment

### Docker

To configure your local environment, and even, to deploy a function you need to download and install [Docker Desktop](https://www.docker.com/products/docker-desktop).

### Apache OpenWhisk on IBM Cloud platform

Download and install [IBM Cloud CLI](https://cloud.ibm.com/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) and [IBM Cloud Functions CLI](https://cloud.ibm.com/openwhisk/learn/cli) to build your functions on IBM Cloud platform. If you want to use the standard [Apache OpenWhisk CLI](https://openwhisk.apache.org/documentation.html#wsk-cli), you can access the link and download the `wsk-cli`.

### OpenFaaS

To install and configure [OpenFaaS](https://openfass.com), you need to install [Docker](https://github.com/victorshinya/docker-functions#docker) in your local machine.
```sh
curl -sSL https://raw.githubusercontent.com/openfaas/faas/master/docker-compose.yml | grep image | awk -F " " '{print $NF}' | xargs -L1 docker pull
```

Setup a single-node cluster.
```sh
docker swarm init
```

Create an account on [Docker Hub](https://hub.docker.com/) and log in.
```sh
docker login
```

Download and install [OpenFaaS CLI](https://openfaas.com).
```sh
curl -sL cli.openfaas.com | sudo sh
```

## Samples

Follow both samples in this repository:
- [Sample C prograaming language on IBM Cloud Functions](https://github.com/victorshinya/docker-faas/blob/master/c-lang#README.md)
- [ImageMagick service on OpenFaaS](https://github.com/victorshinya/docker-faas/blob/master/imagemagick#README.md)
