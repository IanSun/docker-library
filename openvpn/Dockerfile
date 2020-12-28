FROM alpine

ARG VERSION

COPY rootfs/ /

RUN set -ex; \
  apk add --no-cache openvpn=$VERSION

EXPOSE 1194
EXPOSE 1194/udp

VOLUME [ "/etc/openvpn" ]

ENTRYPOINT [ "/sbin/init" ]
