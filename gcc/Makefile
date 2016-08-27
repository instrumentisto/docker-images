# Build GCC image
#
# Usage:
# 	make (container|push|push-tag)

default: container


NAME=quay.io/instrumentisto/gcc
ifndef VERSION
  VERSION=6.1.1
endif
ifndef TAG
  TAG=latest
endif

container:
	docker build -t $(NAME):$(VERSION) ./$(VERSION)/

push: container
	docker push $(NAME):$(VERSION)

push-tag:
	docker tag $(NAME):$(VERSION) $(NAME):$(TAG)
	docker push $(NAME):$(TAG)
