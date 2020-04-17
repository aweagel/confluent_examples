FROM confluentinc/cp-ksql-server:5.4.1

RUN apt-get update \
  && apt-get install -y procps \
  && cd /opt \
  && wget http://client.hub.confluent.io/confluent-hub-client-latest.tar.gz \
  && tar zxvf confluent-hub-client-latest.tar.gz \
  && rm confluent-hub-client-latest.tar.gz \
  && ln -sf /opt/bin/confluent-hub /usr/local/bin/ \
  && confluent-hub install debezium/debezium-connector-postgresql:1.1.0 --no-prompt \
  && cp /opt/share/confluent-hub-components/debezium-debezium-connector-postgresql/lib/* /usr/share/java/ksql-server/
