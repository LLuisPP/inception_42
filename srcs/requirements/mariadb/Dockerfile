FROM debian:bullseye

RUN apt-get update && apt-get install -y mariadb-server \
  && rm -rf /var/lib/apt/lists/*

#MariaDB listen at 0.0.0.0
RUN sed -i 's/^bind-address.*/bind-address=0.0.0.0/' /etc/mysql/mariadb.conf.d/50-server.cnf

COPY tools/entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh

EXPOSE 3306

ENTRYPOINT ["/entrypoint.sh"]
