FROM mysql:8.0.28
# conf
#COPY  ./mysql/my.cnf /etc/mysql/conf.d/my.cnf
#RUN chmod 644 /etc/mysql/conf.d/my.cnf

# dir
RUN mkdir /data
RUN mkdir /data/mysql
RUN mkdir /data/log
RUN mkdir /data/log/mysql
RUN chown -R mysql:mysql /data/mysql
RUN chown -R mysql:mysql /data/log/mysql

# timezone
RUN echo "USE mysql;" > /docker-entrypoint-initdb.d/timezones.sql &&  mysql_tzinfo_to_sql /usr/share/zoneinfo >> /docker-entrypoint-initdb.d/timezones.sql
