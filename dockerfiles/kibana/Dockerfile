# Base image
FROM nginx:1

# Update OS
RUN apt-get update

# Install wget & ca-certificates
RUN apt-get install -y wget ca-certificates

# Install Kibana
RUN cd /tmp && \
    wget https://download.elasticsearch.org/kibana/kibana/kibana-3.1.2.tar.gz && \
    tar xzvf kibana-3.1.2.tar.gz && \
    mv ./kibana-3.1.2/* /usr/share/nginx/html/ && \
    rm ./kibana-3.1.2.tar.gz

# Expose port for web console access
EXPOSE 80
