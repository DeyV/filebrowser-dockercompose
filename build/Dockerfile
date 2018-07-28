FROM hacdias/filebrowser
LABEL maintainer="DP <dawid.polak@mentax.pl>"


FROM alpine
COPY --from=0 /filebrowser /filebrowser

COPY ./unpack /usr/bin/
COPY ./config.json /config.json

RUN apk add --upgrade --no-cache \
      p7zip \
 && apk del --purge \
 && rm -rf /var/cache/apk/*

VOLUME /tmp
VOLUME /srv
EXPOSE 80

ENTRYPOINT ["/filebrowser", "--config", "/config.json"]
