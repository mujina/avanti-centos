FROM centos:latest
MAINTAINER Michael Kirk <mkirk@pugme.co.uk>

ARG BUILD_DATE
ARG BUILD_VERSION

ENV TERM=xterm-256color
ENV LANG=C.UTF-8

RUN yum update -y && \
    yum install -y ruby git wget bzip2

# This is the label schema specification version
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="avanti/centos-base"
LABEL org.label-schema.description="Avanti Base Image"
LABEL org.label-schema.url="http://www.avanti.com"
LABEL org.label-schema.vcs-url="https://TBC"
LABEL org.label-schema.vcs-ref=$VCS_REF
# The organisation that produces this image
LABEL org.label-schema.vendor="Pugme Ltd"
LABEL org.label-schema.version=$BUILD_VERSION
LABEL org.label-schema.docker.cmd="docker run -it pugme/avanti-centos-base /bin/bash"