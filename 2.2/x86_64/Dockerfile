############################################################
# Dockerfile to run an OrientDB (Graph) Container
############################################################

FROM ibmjava:8-sfj-alpine

MAINTAINER Sylvain Corsini <sylvain.corsini@pm.me> (@scorsi)

ENV ORIENTDB_VERSION 2.2.33
ENV ORIENTDB_DOWNLOAD_MD5 163fc4f24c7b7d7a8179a7d10f49903e
ENV ORIENTDB_DOWNLOAD_SHA1 ddf34eda1d03484a2e1ace0cbc4abc3100c86400

ENV ORIENTDB_DOWNLOAD_URL http://central.maven.org/maven2/com/orientechnologies/orientdb-community/$ORIENTDB_VERSION/orientdb-community-$ORIENTDB_VERSION.tar.gz

RUN apk --update add --no-cache tar curl

RUN mkdir /orientdb && \
  wget $ORIENTDB_DOWNLOAD_URL \
  && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c - \
  && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c - \
  && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1 \
  && rm orientdb-community-$ORIENTDB_VERSION.tar.gz \
  && rm -rf /orientdb/databases/*

RUN apk del tar curl \
  && rm -rf /tmp/*


ENV PATH /orientdb/bin:$PATH

VOLUME ["/orientdb/backup", "/orientdb/databases", "/orientdb/config"]

WORKDIR /orientdb

#OrientDb binary
EXPOSE 2424

#OrientDb http
EXPOSE 2480

# Default command start the server
CMD ["server.sh"]
