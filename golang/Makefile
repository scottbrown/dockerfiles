.DEFAULT_GOAL := all
.PHONY: all help deps image tag release

IMAGE_NAME := golang
NAMESPACE := scottbrown
DOCKER_BIN := docker

GO_VERSION := 1.6.2

all: help  ## [DEFAULT] display help

help:  ## displays this message
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'

deps:  ## ensures required project binaries and libs are installed
	@hash $(DOCKER_BIN) > /dev/null || \
		(echo "Install docker to continue"; exit 1)

image:  ## build a new Docker image from this project
	$(DOCKER_BIN) build -t $(IMAGE_NAME) .

tag:  ## tag the Docker image by commit and "latest"
	$(DOCKER_BIN) tag $(IMAGE_NAME) $(NAMESPACE)/$(IMAGE_NAME):$(GO_VERSION)
	$(DOCKER_BIN) tag $(IMAGE_NAME) $(NAMESPACE)/$(IMAGE_NAME):latest

release: tag  ## push the Docker image to Docker Hub
	$(DOCKER_BIN) push $(NAMESPACE)/$(IMAGE_NAME):latest
	$(DOCKER_BIN) push $(NAMESPACE)/$(IMAGE_NAME):$(GO_VERSION)

