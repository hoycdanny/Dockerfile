FROM ubuntu:14.04
MAINTAINER Danny,Ho <danny.ho@hpe.com>
RUN apt-get update
RUN apt-get -y install \
	             	nginx
COPY docker-entrypoint.sh /usr/local/bin/
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT sh entrypoint.sh && bash
EXPOSE 80
#docker run -tdi -e PROXY_PASS=https://www.nginx.com -e PROXY_PATH=nginx -p 80:80 nginx-reverse-proxy
