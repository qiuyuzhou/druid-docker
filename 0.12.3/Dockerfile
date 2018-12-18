FROM openjdk:9-jdk

ENV DROID_VERSION="0.12.3"
ENV DRUID_HOME=/opt/druid
ENV DRUID_DATA=/var/druid

RUN curl -O http://static.druid.io/artifacts/releases/druid-${DROID_VERSION}-bin.tar.gz \
    && tar -xzf druid-${DROID_VERSION}-bin.tar.gz -C /opt \
    && rm druid-${DROID_VERSION}-bin.tar.gz \
    && ln -s /opt/druid-${DROID_VERSION} ${DRUID_HOME}

WORKDIR $DRUID_HOME
VOLUME [${DRUID_DATA}]

COPY run.sh $DRUID_HOME/bin/run.sh

# Expose ports:
# - 8081: HTTP (coordinator)
# - 8082: HTTP (broker)
# - 8083: HTTP (historical)
# - 8090: HTTP (overlord)
EXPOSE 8081-8083 8090

ENTRYPOINT ["bin/run.sh"]
