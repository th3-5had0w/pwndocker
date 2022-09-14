MNTDIR ?= $(shell pwd)

build:
	docker build -t pwn1604 . --no-cache
stop:
	docker container rm -f pwn1604 2>/dev/null
run:
	docker container rm -f pwn1604 2>/dev/null
	docker run --cap-add=SYS_PTRACE --security-opt seccomp=unconfined --security-opt apparmor=unconfined -h pwn1604 --name pwn1604 -v $(MNTDIR):/workspace -it -d pwn1604
exe:
	docker exec -it pwn1604 /bin/bash
