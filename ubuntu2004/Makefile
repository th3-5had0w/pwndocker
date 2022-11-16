MNTDIR ?= $(shell pwd)

build:
	docker build -t pwn2004 . --no-cache
stop:
	docker container rm -f pwn2004 2>/dev/null | true
run:
	docker container rm -f pwn2004 2>/dev/null | true
	docker run --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --security-opt apparmor=unconfined -h pwn2004 --name pwn2004 -v $(MNTDIR):/workspace -it -d pwn2004
exe:
	docker exec -it pwn2004 /bin/bash
