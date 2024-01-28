FROM alpine
COPY --from=ckware/asset-upnp:R6.7 /opt/ /opt/
RUN  ln -s "$(find /opt/ -mindepth 1 -maxdepth 1 -type d | head -n 1)/bin/AssetUPnP" /usr/local/bin/asset
RUN  mkdir /data
RUN adduser -D user
ENV  _APPDATA_OVERRIDE=/data
STOPSIGNAL SIGINT
CMD [ "asset" ]
USER user
