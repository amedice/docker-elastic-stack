#docker build --rm -t amedice/logstash .
#docker run -d --link elasticsearch1 --network=dockerelasticstack_default --name logstash1 amedice/logstash
#docker exec -it logstash1 /bin/bash
#docker rm -f logstash1

FROM logstash
MAINTAINER Alex S. Médice <alex.medice@gmail.com>

#RUN logstash-plugin install logstash-filter-de_dot

#COPY log-app1.xml /var/log/log-app1.xml

#COPY logstash-app.conf /etc/logstash/conf.d/logstash-app.conf
#COPY logstash-server.conf /etc/logstash/conf.d/logstash-server.conf

#CMD ["-f", "/etc/logstash/config.d/logstash-app.conf"]

COPY ./exemple-csv.conf /etc/logstash/conf.d/exemple-csv.conf
COPY ./onibus.csv /tmp/onibus.csv
#logstash -f /etc/logstash/conf.d/exemple-csv.conf -l /tmp/log1.txt --debug
CMD ["-f", "/etc/logstash/conf.d/exemple-csv.conf"]