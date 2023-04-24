FROM ubuntu:20.10
RUN cp /etc/apt/sources.list /etc/apt/sources.list.bak \
	&& sed -i -re 's/([a-z]{2}\.)?archive.ubuntu.com|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list \
	&& apt update \
	&& apt upgrade \
	&& apt install -y python3 \
	&& apt install -y wget \
	&& cd /usr/bin \
	&& ln -s python3 python
EXPOSE 80
CMD ["python", "-m", "http.server", "-d", "/mnt/", "80"]