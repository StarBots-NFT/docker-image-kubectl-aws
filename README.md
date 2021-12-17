# Dockerized [kubectl](https://github.com/kubernetes/kubectl) with [doctl](https://github.com/digitalocean/doctl)

This repository contains Dockerized [kubectl](https://github.com/kubernetes/kubectl) with [doctl](https://github.com/digitalocean/doctl). Repository name in Docker Hub: [particle4dev/kubectl-doctl](https://hub.docker.com/r/particle4dev/kubectl-doctl)

**The problem** that this image tried to solved:

When you get the credentials of Digitalocean Kubernetes cluster to your local and use it with Kubeclt Docker Image, it won't work because Kubeclt command needs Doctl to connect to cluster. I solved this issue by merging Kubectl and Doctl into one image. See Usage section to see how to use this.

<br />

[![CircleCI](https://circleci.com/gh/particle4dev/docker-image-kubectl-doctl.svg?style=svg)](https://circleci.com/gh/particle4dev/docker-image-kubectl-doctl)

## Configuration

This docker image contains the following software stack:

- Alpine

- [kubectl](https://github.com/kubernetes/kubectl)

- [aws](https://github.com/aws/aws-cli)

## Usage

#### Usage

- kubectl

```sh
# get k8s nodes
$ docker run \
--rm \
--env-file $ENV_FILE \
-v <path_to_save_kube_config>/config:/root/.kube/config \
particle4dev/kubectl-doctl kubectl get nodes
```

- aws ???

```sh
# get k8s nodes
$ docker run \
--rm \
--env-file $ENV_FILE \
-v <path_to_save_kube_config>/config:/root/.kube/config \
particle4dev/kubectl-doctl kubectl get nodes
```

### How to add a new version

- Step1: Open VERSIONS file

- Step2: Add version you wanted in bottom the file. E.g

```
kubectl-1.18.6-aws-2.4.6
```

### How to run manually

export IMAGE_NAME="kubectl-aws"

export CI_PROJECT_DIR="$(pwd)"

export CI_IMAGE="$DOCKER_HUB_USER/${IMAGE_NAME}"

export CI_REGISTRY_IMAGE="docker.io/${CI_IMAGE}"
