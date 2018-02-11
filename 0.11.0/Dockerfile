FROM openjdk:9-jdk

ENV DROID_VERSION="0.11.0"

CMD curl -O http://static.druid.io/artifacts/releases/druid-${DROID_VERSION}-bin.tar.gz \
    && tar -xzf druid-${DROID_VERSION}-bin.tar.gz -C /opt \
    && rm druid-${DROID_VERSION}-bin.tar.gz \
    && ln -s /opt/druid-${DROID_VERSION} /opt/druid

VOLUME ["/var/druid"]
