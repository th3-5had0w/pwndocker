MNTDIR ?= $(shell pwd)

build:
	docker build -t pwn2204 . --no-cache
stop:
	docker container rm -f pwn2204 2>/dev/null | true
run:
	docker container rm -f pwn2204 2>/dev/null | true
	docker run --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --security-opt apparmor=unconfined -h pwn2204 --name pwn2204 -v $(MNTDIR):/workspace -it -d pwn2204
exe:
	docker exec -it pwn2204 /bin/bash
