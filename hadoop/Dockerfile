FROM centos:centos7.8.2003
MAINTAINER luoshiying(lquartz@126.com)

LABEL Description="CentOS 7.8 + hadoop"

# install java
ARG JAVA_VERSION=7
ARG JAVA_RELEASE=JDK

RUN set -eux && \
    pkg="java-1.$JAVA_VERSION.0-openjdk" && \
    if [ "$JAVA_RELEASE" = "JDK" ]; then \
        pkg="$pkg-devel"; \
    else \
        pkg="$pkg-headless"; \
    fi; \
    yum install -y "$pkg" && \
    yum clean all && \
    rm -rf /var/cache/yum

COPY profile.d/java.sh /etc/profile.d/

ENV JAVA_HOME=/usr

# install hadoop


CMD ["/bin/bash"]
