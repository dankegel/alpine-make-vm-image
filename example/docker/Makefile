test: simple-priv simple-cap

BASE=ubuntu:latest
OPTS=

simple-priv:
	cp ../../alpine-make-vm-image .
	docker build --build-arg BASE=$(BASE) --build-arg OPTS=$(OPTS) -t simple .
	rm alpine-make-vm-image
	rm -rf out
	mkdir out
	docker run -v $$(pwd)/out:/out \
		--privileged \
		-t simple

simple-cap:
	cp ../../alpine-make-vm-image .
	docker build --build-arg BASE=$(BASE) --build-arg OPTS=$(OPTS) -t simple .
	rm alpine-make-vm-image
	rm -rf out
	mkdir out
	docker run -v $$(pwd)/out:/out \
		-t simple
		--device /dev/fuse \
		--cap-add SYS_ADMIN \
		--security-opt apparmor:unconfined
