ARG BASE
FROM ${BASE}
ENV DEBIAN_FRONTEND=noninteractive
ARG OPTS
ENV OPTS=${OPTS}
RUN \
  apt-get update && apt-get install -y --no-install-recommends libguestfs-tools wget linux-image-$(uname -r) linux-modules-$(uname -r)
COPY alpine-make-vm-image .
CMD sh -x alpine-make-vm-image --branch 3.12 --image-format qcow2 --image-size 250M ${OPTS} -- out/simple.qcow2
