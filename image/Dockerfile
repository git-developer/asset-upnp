ARG SOURCE=ckware/asset-upnp:R6.7
FROM $SOURCE AS source

FROM alpine AS runtime
COPY --from=source /opt/ /opt/
RUN  ln -s "$(find /opt/ -mindepth 1 -maxdepth 1 -type d | head -n 1)/bin/AssetUPnP" /usr/local/bin/asset
RUN  mkdir /data
ENV  _APPDATA_OVERRIDE=/data
STOPSIGNAL SIGINT
CMD  asset
RUN adduser -D user
USER user
