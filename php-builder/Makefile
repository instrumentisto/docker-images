# Build PHP builder image
#
# Usage:
# 	make [VERSION=...] [TAGS=tag1,tag2,...] (container|push|push-tags)

default: container


NAME = quay.io/instrumentisto/php-builder
VERSION ?= 7.0.11
TAGS ?= 7,7.0,latest

comma:= ,
empty:=
space:= $(empty) $(empty)
tags := $(subst $(comma), $(space), $(TAGS))

container:
	docker build -t $(NAME):$(VERSION) ./$(VERSION)/

container-nocache:
	docker build --no-cache -t $(NAME):$(VERSION) ./$(VERSION)/

push: container
	docker push $(NAME):$(VERSION)

push-tags:
	$(foreach tag, $(tags), \
		docker tag $(NAME):$(VERSION) $(NAME):$(tag); \
		docker push $(NAME):$(tag); \
	)
