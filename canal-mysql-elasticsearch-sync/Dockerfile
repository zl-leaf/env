FROM java:8

RUN curl -LO https://github.com/starcwang/canal_mysql_elasticsearch_sync/releases/download/1.0.3/canal-mysql-elasticsearch-sync-1.0.3.tar.gz
RUN mkdir /usr/local/canalsync
RUN tar -zxvf canal-mysql-elasticsearch-sync-1.0.3.tar.gz  -C /usr/local/canalsync
RUN rm canal-mysql-elasticsearch-sync-1.0.3.tar.gz


COPY conf /usr/local/canalsync/conf
COPY bin/startup.sh /usr/local/canalsync/bin/startup.sh
RUN chmod -R a+x /usr/local/canalsync/bin/startup.sh
RUN touch /usr/local/canalsync/logs/info.log

WORKDIR /usr/local/canalsync/bin/
CMD /usr/local/canalsync/bin/stop.sh && /usr/local/canalsync/bin/startup.sh && tail -f /usr/local/canalsync/logs/info.log