FROM ?=

REGISTRY ?= quay.io
REGISTRY_ORG ?= ai-lab
IMAGE_NAME ?= amd-bootc
IMAGE_TAG ?= latest

CONTAINER_TOOL ?= podman
CONTAINER_TOOL_EXTRA_ARGS ?=

.PHONY: image
image:
	"${CONTAINER_TOOL}" build \
		--file Containerfile \
		--tag "${REGISTRY}/${REGISTRY_ORG}/${IMAGE_NAME}:${IMAGE_TAG}" \
		$(FROM:%=--from=%) \
		${CONTAINER_TOOL_EXTRA_ARGS}
