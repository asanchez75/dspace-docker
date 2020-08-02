# dspace-docker
[![Build Status](https://travis-ci.org/4Science/dspace-docker.svg?branch=master)](https://travis-ci.org/4Science/dspace-docker)


[Docker images for dspace &amp; dspace-cris](https://hub.docker.com/r/4science/dspace-cris/) (experimental)


### Getting Started

To get the DSpace-CRIS 5.7.0 up and running please execute:
This may take a while because the Docker image needs to be created first and therefore the source and dependencies need to be downloaded.
Afterwards `mvn package` is executed which also takes time.

```
git clone https://github.com/4science/dspace-docker
cd dspace-docker
docker-compose up -d

```

### Manual build

Start from file `VERSION`, dspace-5_x_x-cris is the most up-to-date github 4science branch

```
DSPACE_VERSION=dspace-5_x_x-cris
DSPACE_VCS_URL=https://github.com/4science/dspace
DOCKER_IMAGE_NAME=asanchez75/dspace-cris
DOCKER_TAG=5.10.0
```
The values for DOCKER_IMAGE_NAME and DOCKER_TAG must also be the same for the file `docker-compose.yml`

```
  dspace:
    image: asanchez75/dspace-cris:5.10.0
``` 

Then, 

* run `./build.sh`
* run `docker-compose up -d postgres && docker-compose up -d dspace`
* edit file `./dspace-cris/config/dspace.cfg`
