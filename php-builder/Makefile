# Build PHP builder image
#
# Usage:
# 	make (container|push|push-tags) [VERSION=...] [TAGS=tag1,tag2,...] [no-cache=(yes|no)]
# 	make all [VERSION=...] [TAGS=tag1,tag2,...] [no-cache=(yes|no)]
# 	make everything [no-cache=(yes|no)]

default: container


NAME := quay.io/instrumentisto/php-builder
VERSION ?= 7.0.12
TAGS ?= 7,7.0,latest
no-cache ?= no

comma:= ,
empty:=
space:= $(empty) $(empty)
eq = $(if $(or $(1),$(2)),$(and $(findstring $(1),$(2)),\
                                $(findstring $(2),$(1))),1)

tags = $(subst $(comma), $(space), $(TAGS))

no-cache-arg = $(if $(call eq, $(no-cache), yes), --no-cache, $(empty))


container:
	docker build $(no-cache-arg) -t $(NAME):$(VERSION) ./$(VERSION)/

push: container
	docker push $(NAME):$(VERSION)

push-tags:
	$(foreach tag, $(tags), \
		docker tag $(NAME):$(VERSION) $(NAME):$(tag); \
		docker push $(NAME):$(tag); \
	)


all: | container push push-tags

everything:
	make all VERSION=5.6.27 TAGS=5,5.6
	make all VERSION=7.0.12 TAGS=7,7.0,latest


.PHONY: container push push-tags all everything
