.PHONY: build

VERSION = 2.2.0

build:
	sudo docker build --build-arg VERSION=$(VERSION) -t "att/ansible-mysql:v$(VERSION)" .

default: build
