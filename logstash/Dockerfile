#docker build --rm -t amedice/logstash .
#docker run -d --name logstash amedice/logstash
#docker exec -it logstash /bin/bash
#docker rm -f logstash

FROM logstash
MAINTAINER Alex S. Médice <alex.medice@gmail.com>

#RUN logstash-plugin install logstash-filter-de_dot

#COPY logstash-app.conf /etc/logstash/config.d/logstash-app.conf
#COPY logstash-server.conf /etc/logstash/config.d/logstash-server.conf

#CMD ["-f", "/etc/logstash/config.d/logstash-app.conf"]