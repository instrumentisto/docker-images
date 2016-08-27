# Build GCC image
#
# Usage:
# 	make (container|push)

default: container


NAME=quay.io/instrumentisto/gcc
ifndef VERSION
  VERSION=6.1.1
endif

container:
	docker build -t $(NAME):$(VERSION) ./$(VERSION)/

push: container
	docker push $(NAME):$(VERSION)
