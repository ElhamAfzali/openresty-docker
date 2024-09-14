# openresty-docker
# OpenResty Docker

This repository contains the Docker build files for creating and managing a Docker image of [OpenResty](https://openresty.org/), a full-fledged web platform that integrates NGINX and LuaJIT for developing high-performance web applications. This setup is built on top of Debian Bullseye and includes additional OpenResty modules and tools for extended functionality.

## Table of Contents
- [Overview](#overview)
- [Requirements](#requirements)
- [Setup in PyCharm](#setup-in-pycharm)
- [Docker Image Details](#docker-image-details)
- [How to Use](#how-to-use)
  - [Building the Image](#building-the-image)
  - [Pushing the Image](#pushing-the-image)
- [Continuous Integration](#continuous-integration)
- [Exposed Ports](#exposed-ports)
- [Environment Variables](#environment-variables)
- [Volumes](#volumes)
- [Maintainer](#maintainer)

## Overview

This repository provides a Dockerfile and scripts to build and push a custom OpenResty Docker image with various OpenResty modules enabled for flexibility and customization.

## Requirements

- [Docker](https://docs.docker.com/get-docker/)
- A [Docker Hub](https://hub.docker.com/) account
- [PyCharm](https://www.jetbrains.com/pycharm/) with Docker support

## Setup in PyCharm

To work with this project in PyCharm:

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/openresty_docker.git
    ```

2. Open the project in PyCharm by selecting `File -> Open` and navigating to the cloned repository folder.

3. Ensure Docker is configured in PyCharm:
   - Go to `File -> Settings -> Build, Execution, Deployment -> Docker`.
   - Add a new Docker configuration using the "+" button, and ensure it points to the correct Docker instance (e.g., Docker Desktop or system Docker).

4. Add a Docker interpreter in PyCharm (optional):
   - Go to `File -> Settings -> Project: <Your Project Name> -> Python Interpreter`.
   - Click the settings icon, then select `Add...`, and choose `Docker`.
   - In the `Docker` tab, configure the image and interpreter as needed.

5. To run the provided bash scripts (`build.sh` and `push.sh`):
   - Open the `Terminal` in PyCharm (`View -> Tool Windows -> Terminal`).
   - Run the build and push commands from the terminal.

## Docker Image Details

- **Base Image**: `debian:bullseye`
- **OpenResty Version**: `1.21.4.1`
- **Modules Enabled**:
  - File AIO
  - HTTP Modules: addition, auth request, dav, flv, geoip, gunzip, gzip_static, image filter (dynamic), mp4, random index, realip, secure link, slice, ssl, stub status, sub, v2, xslt (dynamic)
  - Stream and Mail Modules: geoip, realip, ssl
  - Support for pcre-jit, ipv6, md5-asm, sha1-asm, threads

## How to Use

### Building the Image

To build the OpenResty Docker image, run the following script in PyCharm’s terminal:

```bash
./build.sh
```
Ensure Docker Hub credentials are set as secrets (`DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN`).

## Continuous Integration
GitHub Actions automates the build and push process for the `master` branch. This is defined in `.github/workflows/workflow.yml`.

## Exposed Ports
- **80**: HTTP
- **443**: HTTPS

## Maintainer
**Majid Ettehadi**

- Docker Hub: [majid7221](https://hub.docker.com/u/majid7221)

