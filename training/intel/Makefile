FROM ?= 

REGISTRY ?= quay.io
REGISTRY_ORG ?= ai-lab
IMAGE_NAME ?= intel-gaudi-bootc
IMAGE_TAG ?= latest

CONTAINER_TOOL ?= podman
CONTAINER_TOOL_EXTRA_ARGS ?=

DRIVER_VERSION ?=
KERNEL_VERSION ?= 

.PHONY: image
image:
	"${CONTAINER_TOOL}" build \
		--file Containerfile \
		--tag "${REGISTRY}/${REGISTRY_ORG}/${IMAGE_NAME}:${IMAGE_TAG}" \
		$(FROM:%=--build-arg BASEIMAGE=%) \
		$(DRIVER_VERSION:%=--build-arg DRIVER_VERSION=%) \
		$(KERNEL_VERSION:%=--build-arg KERNEL_VERSION=%) \
		${CONTAINER_TOOL_EXTRA_ARGS}
