FROM java:8-jdk

WORKDIR /usr/local
RUN wget http://dl.mycat.io/1.6-RELEASE/Mycat-server-1.6-RELEASE-20161028204710-linux.tar.gz \
    && tar -zxvf Mycat-server-1.6-RELEASE-20161028204710-linux.tar.gz

ADD schema.xml /usr/local/mycat/conf/schema.xml
ADD server.xml /usr/local/mycat/conf/server.xml

RUN chmod -R 755 /usr/local/mycat/bin
RUN ln -s /usr/local/mycat/bin/mycat /usr/local/bin/mycat

WORKDIR /usr/local/mycat/bin

ENTRYPOINT ["mycat"]

CMD ["console"]