FROM java:7

RUN curl -LO https://github.com/alibaba/canal/releases/download/canal-1.0.24/canal.deployer-1.0.24.tar.gz
RUN mkdir /usr/local/canal
RUN tar -zxvf canal.deployer-1.0.24.tar.gz  -C /usr/local/canal
RUN rm canal.deployer-1.0.24.tar.gz

RUN chmod -R a+x /usr/local/canal/bin/startup.sh

COPY conf /usr/local/canal/conf

WORKDIR /usr/local/canal/bin/

CMD /usr/local/canal/bin/stop.sh && /usr/local/canal/bin/startup.sh >> /usr/local/canal/logs/canal.log && tail -f /usr/local/canal/logs/canal.log