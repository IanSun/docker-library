FROM alpine

COPY get-file /usr/bin/

ARG VERSION

RUN set -ex; \
  apk add --no-cache curl; \
  mkdir -p /usr/share/kcptun; \
  get-file $VERSION | \
    tar -xzC /usr/share/kcptun; \
  cd /usr/share/kcptun; \
  find . -name "client_*" -type f -exec mv {} kcptun +;


FROM scratch

COPY --from=0 /usr/share/kcptun/kcptun /bin/

CMD [ "/bin/kcptun" ]
