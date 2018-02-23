FROM logstash:5.6

ADD conf.d/*.conf /etc/logstash/conf.d

# install the plugin of logstash

CMD logstash -f /etc/logstash/conf.d/