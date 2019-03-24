FROM pugme/avanti-centos-base:latest
MAINTAINER Michael Kirk <mkirk@pugme.co.uk>

ARG BUILD_DATE
ARG BUILD_VERSION
ARG PHP_VERSION=72

ENV TERM=xterm-256color
ENV LANG=C.UTF-8

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm && \
    yum install -y http://rpms.remirepo.net/enterprise/remi-release-7.rpm && \
    yum-config-manager --enable remi-php${PHP_VERSION}

RUN yum install -y httpd php

RUN echo '<?php phpinfo(); ?>' > /var/www/html/index.php

EXPOSE 80

CMD  ["/usr/sbin/httpd","-D","FOREGROUND"]

# This is the label schema specification version
LABEL org.label-schema.schema-version="1.0"
LABEL org.label-schema.build-date=$BUILD_DATE
LABEL org.label-schema.name="avanti/centos-php"
LABEL org.label-schema.description="Avanti PHP Web Server"
LABEL org.label-schema.url="http://www.avanti.com"
LABEL org.label-schema.vcs-url="https://TBC"
LABEL org.label-schema.vcs-ref=$VCS_REF
# The organisation that produces this image
LABEL org.label-schema.vendor="Pugme Ltd"
LABEL org.label-schema.version=$BUILD_VERSION
LABEL org.label-schema.docker.cmd="docker run -d --name avanti-centos-php${PHP_VERSION} -p 80:8080 pugme/avanti-centos-php${PHP_VERSION}"
