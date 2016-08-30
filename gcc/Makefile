# Build GCC image
#
# Usage:
# 	make [VERSION=...] [TAGS=tag1,tag2,...] (container|push|push-tags)

default: container


NAME = quay.io/instrumentisto/gcc
ifndef VERSION
  VERSION = 6.2.0
endif
ifndef TAGS
  TAGS = latest
endif

comma:= ,
empty:=
space:= $(empty) $(empty)
tags := $(subst $(comma), $(space), $(TAGS))

container:
	docker build -t $(NAME):$(VERSION) ./$(VERSION)/

push: container
	docker push $(NAME):$(VERSION)

push-tags:
	$(foreach tag, $(tags), \
		docker tag $(NAME):$(VERSION) $(NAME):$(tag); \
		docker push $(NAME):$(tag); \
	)
