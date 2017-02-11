#docker build -t amedice/elasticsearch .
#docker run -d -it -p 9200:9200 --name elasticsearch amedice/elasticsearch
#docker exec -it elasticsearch /bin/bash
#docker rm -f elasticsearch

FROM centos
MAINTAINER Alex S. Médice <alex.medice@gmail.com>

# Upgrading system
RUN yum -y upgrade

# Install tools
RUN yum -y install wget vim

# Create user
RUN adduser -m elasticsearch
WORKDIR /home/elasticsearch

# Install Java
COPY jre-8u121-linux-x64.rpm /home/elasticsearch/
RUN rpm -ivh jre-8u121-linux-x64.rpm
RUN rm jre-8u121-linux-x64.rpm

# Install Elasticsearch
RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.0.2.tar.gz
RUN sha1sum elasticsearch-5.0.2.tar.gz 
RUN tar -xzf elasticsearch-5.0.2.tar.gz
RUN chown -Rf elasticsearch:elasticsearch ./elasticsearch-5.0.2
RUN rm elasticsearch-5.0.2.tar.gz

# Run
USER elasticsearch
#RUN ./elasticsearch-5.0.2/bin/elasticsearch