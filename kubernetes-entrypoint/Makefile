.PHONY: build

VERSION = v0.1.0

build:
	sudo docker build --build-arg VERSION=$(VERSION) -t "att/kubernetes-entrypoint:$(VERSION)" .

default: build
