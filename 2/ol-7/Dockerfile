FROM bitnami/oraclelinux-runtimes:7-r310
LABEL maintainer "Bitnami <containers@bitnami.com>"

# Install required system packages and dependencies
RUN install_packages bzip2-libs ca-certificates curl gcc gcc-c++ git glibc keyutils-libs krb5-libs libcom_err libselinux libtool make ncurses-libs nss-softokn-freebl openssl-libs patch pcre pkgconfig readline sqlite unzip wget zlib
RUN wget -nc -P /tmp/bitnami/pkg/cache/ https://downloads.bitnami.com/files/stacksmith/python-2.7.16-0-linux-x86_64-ol-7.tar.gz && \
    echo "f1818dfd2f72ba498d54702d4e6aa44fcdecc1f0b1fc7d99703e74b4626f6395  /tmp/bitnami/pkg/cache/python-2.7.16-0-linux-x86_64-ol-7.tar.gz" | sha256sum -c - && \
    tar -zxf /tmp/bitnami/pkg/cache/python-2.7.16-0-linux-x86_64-ol-7.tar.gz -P --transform 's|^[^/]*/files|/opt/bitnami|' --wildcards '*/files' && \
    rm -rf /tmp/bitnami/pkg/cache/python-2.7.16-0-linux-x86_64-ol-7.tar.gz

ENV BITNAMI_APP_NAME="python" \
    BITNAMI_IMAGE_VERSION="2.7.16-ol-7-r64" \
    PATH="/opt/bitnami/python/bin:$PATH"

EXPOSE 8000

WORKDIR /app
CMD [ "python" ]
