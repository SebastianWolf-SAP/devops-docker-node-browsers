# Node Browsers Image

[![REUSE status](https://api.reuse.software/badge/github.com/SAP/devops-docker-node-browsers)](https://api.reuse.software/info/github.com/SAP/devops-docker-node-browsers)

This [_Dockerfile_](https://docs.docker.com/engine/reference/builder/) can be used in _Continuous Delivery_ (CD) pipelines for SAP development projects.
The image is optimized for use with project ["Piper"](https://github.com/SAP/jenkins-library) on [Jenkins](https://jenkins.io/).
Docker containers simplify your CD tool setup, encapsulating tools and environments that are required to execute pipeline steps.

If you want to learn how to use project "Piper" please have a look at [the documentation](https://github.com/SAP/jenkins-library/blob/master/README.md).
Introductory material and a lot of SAP scenarios not covered by project "Piper" are described in our [Continuous Integration Best Practices](https://developers.sap.com/tutorials/ci-best-practices-intro.html).

## About this repository

Dockerfile for an image with node and web browsers.
This image is intended to be used for end to end tests of web applications in Jenkins pipelines.

## Download

This image is published to Docker Hub and can be pulled via the command

```
docker pull ppiper/node-browsers
```

The default tag `latest` contains node 10 for compatibility reasons with approuter, which is a Maintenance LTS and will be end of life after 2021-04-30.

For node-12 or node-14, use the tag `12-buster` or `14-buster`:

```
docker pull ppiper/node-browsers:12-buster
docker pull ppiper/node-browsers:14-buster
```

## Build

To build this image locally, open a terminal in the directory of the Dockerfile and run

```
docker build --build-arg=BASE_IMAGE_TAG=10-buster -t ppiper/node-browsers .
```

Where the `BASE_IMAGE_TAG=10-buster` build argument can be replaced with `BASE_IMAGE_TAG=12-buster` or `BASE_IMAGE_TAG=14-buster`.
The given tag **must** exist in the [node](https://hub.docker.com/_/node) base image **and** use Debian GNU/Linux.

## Usage

See this [blog post](https://blogs.sap.com/2017/12/11/sap-s4hana-cloud-sdk-end-to-end-tests-against-secured-applications/) for usage of this image in a Jenkins pipeline based on `ppiper/jenkins-master`.

## Licensing

Copyright 2017-2021 SAP SE or an SAP affiliate company and devops-docker-node-browsers contributors. Please see our [LICENSE](LICENSE) for copyright and license information. Detailed information including third-party components and their licensing/copyright information is available [via the REUSE tool](https://api.reuse.software/info/github.com/SAP/devops-docker-node-browsers).