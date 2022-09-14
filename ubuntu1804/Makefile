MNTDIR ?= $(shell pwd)

build:
	docker build -t pwn1804 . --no-cache
stop:
	docker container rm -f pwn1804 2>/dev/null
run:
	docker container rm -f pwn1804 2>/dev/null
	docker run --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --security-opt apparmor=unconfined -h pwn1804 --name pwn1804 -v $(MNTDIR):/workspace -it -d pwn1804
exe:
	docker exec -it pwn1804 /bin/bash
