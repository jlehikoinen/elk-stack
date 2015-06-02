FROM debian:jessie

RUN apt-get update && \
    apt-get install -y openjdk-7-jre wget

ENV JAVA_HOME /usr/lib/jvm/java-6-openjdk-amd64

# Install Elasticsearch
RUN wget https://download.elasticsearch.org/elasticsearch/elasticsearch/elasticsearch-1.4.0.tar.gz -O elasticsearch.tar.gz && tar zxf elasticsearch.tar.gz && mv elasticsearch-* /opt/elasticsearch && rm -rf /tmp/*

# Copy Elasticsearch config file from host to container /opt
COPY elasticsearch.yml /opt/elasticsearch/config/elasticsearch.yml

# Expose needed ports
EXPOSE 9200
EXPOSE 9300

# Create a mountpoint for host or other containers
VOLUME /opt/elasticsearch/data

# Container can run as an executable
ENTRYPOINT ["/opt/elasticsearch/bin/elasticsearch"]
