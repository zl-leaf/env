FROM mysql:5.7

MAINTAINER Mahmoud Zalt <mahmoud@zalt.me>

#####################################
# Set Timezone
#####################################

ARG TZ=UTC
ENV TZ ${TZ}
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ADD my.cnf /etc/mysql/conf.d/my.cnf

USER mysql

CMD ["mysqld"]

EXPOSE 3306
