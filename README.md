# Dockerized [kubectl](https://github.com/kubernetes/kubectl) with [aws](https://github.com/aws/aws-cli)

This repository contains Dockerized [kubectl](https://github.com/kubernetes/kubectl) with [aws](https://github.com/aws/aws-cli). Repository name in Docker Hub: [namstarbots/kubectl-aws](https://hub.docker.com/r/namstarbots/kubectl-aws)

**The problem** that this image tried to solved:

When you get the credentials of Digitalocean Kubernetes cluster to your local and use it with Kubeclt Docker Image, it won't work because Kubeclt command needs AWS CLI to connect to cluster. I solved this issue by merging Kubectl and AWS CLI into one image. See Usage section to see how to use this.

<br />

[![CircleCI](https://circleci.com/gh/StarBots-NFT/docker-image-kubectl-aws/tree/master.svg?style=svg)](https://circleci.com/gh/StarBots-NFT/docker-image-kubectl-aws/tree/master)

## Configuration

This docker image contains the following software stack:

- Alpine

- [kubectl](https://github.com/kubernetes/kubectl)
    
    - https://github.com/kubernetes/kubectl/tags
    
- [aws](https://github.com/aws/aws-cli)

    - https://github.com/aws/aws-cli/blob/v2/CHANGELOG.rst

## Usage

#### Usage

- kubectl

```sh
# get k8s nodes
$ docker run \
--rm \
--env-file $ENV_FILE \
-v <path_to_save_kube_config>/config:/root/.kube/config \
particle4dev/kubectl-aws kubectl get nodes
```

- aws

```sh
# show aws cli version
$ docker run \
--rm \
--env-file $ENV_FILE \
particle4dev/kubectl-aws aws --version
```

### How to add a new version

- Step1: Open VERSIONS file

- Step2: Add version you wanted in bottom the file. E.g

```
kubectl-1.18.6-aws-2.4.6
```
