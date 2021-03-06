FROM mysql:5.7

COPY schema.sql /docker-entrypoint-inidb.d/

EXPOSE 3306

VOLUME ["/backup/"]