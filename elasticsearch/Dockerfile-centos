#docker build --rm -t amedice/elasticsearch .
#docker run -d -it -v /sys/fs/cgroup:/sys/fs/cgroup:ro -p 9200:9200 -p 9300:9300 --name elasticsearch amedice/elasticsearch
#docker exec -it elasticsearch /bin/bash
#docker rm -f elasticsearch

FROM amedice/centos
MAINTAINER Alex S. Médice <alex.medice@gmail.com>

# Upgrading system
RUN yum -y upgrade

# Install tools
RUN yum -y install wget vim iptables-services

# Create user
RUN adduser -m elasticsearch
WORKDIR /home/elasticsearch

# Install Java
COPY jre-8u121-linux-x64.rpm /home/elasticsearch/
RUN rpm -ivh jre-8u121-linux-x64.rpm
RUN rm jre-8u121-linux-x64.rpm

# Instal Elasticsearch
RUN rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
RUN wget https://artifacts.elastic.co/downloads/elasticsearch/elasticsearch-5.0.2.rpm
RUN sha1sum elasticsearch-5.0.2.rpm 
RUN rpm --install elasticsearch-5.0.2.rpm

# Run
ENV ES_JAVA_OPTS='-Xms512m -Xmx512m'
EXPOSE 9200 9300
RUN systemctl daemon-reload
RUN systemctl enable elasticsearch.service
RUN systemctl start elasticsearch.service

CMD ["/usr/sbin/init"]