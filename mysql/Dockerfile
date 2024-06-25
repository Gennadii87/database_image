FROM mysql:lts

ENV MYSQL_DATABASE=my_sql_docker
ENV MYSQL_ROOT_PASSWORD=supersecret

RUN touch /docker-entrypoint-initdb.d/init.sql

RUN echo "GRANT ALL PRIVILEGES ON ${MYSQL_DATABASE}.* TO 'root'@'%';" > /docker-entrypoint-initdb.d/init.sql

VOLUME /var/lib/mysql

EXPOSE 3306

CMD ["mysqld"]
