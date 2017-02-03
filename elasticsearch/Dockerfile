#docker build -t amedice/elasticsearch .
#docker run -d -it -p 9200:9200 --name elasticsearch amedice/elasticsearch
#docker exec -it elasticsearch /bin/bash
#docker rm -f elasticsearch

FROM centos
MAINTAINER Alex S. Médice <alex.medice@gmail.com>

# Upgrading system
RUN yum -y upgrade

# Install Java
RUN yum install -y java-1.8.0-openjdk