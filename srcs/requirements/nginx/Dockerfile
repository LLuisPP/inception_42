FROM debian:bullseye

RUN apt-get update && apt-get -y upgrade && apt-get install -y \
	nginx \
	&& rm -rf /var/lib/apt/lists/*

CMD ["sleep", "infinity"]

