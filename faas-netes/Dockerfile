FROM ubuntu:14.04
MAINTAINER Danny,Ho <danny.ho@hpe.com>
RUN apt-get update
RUN apt-get -y install \
                git
RUN sed -e '1 a/ $(whoami)' /etc/hosts
RUN git clone https://github.com/alexellis/faas-netes
WORKDIR faas-netes
RUN kubectl apply -f ./faas.yml,monitoring.yml,rbac.yml
#COPY docker-entrypoint.sh /usr/local/bin/
#RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh
#ENTRYPOINT sh entrypoint.sh && bash
EXPOSE 31112 31119
