FROM ubuntu:14.04
MAINTAINER Danny,Ho <danny.ho@hpe.com>
ENV JENKINS_VERSION jenkins_2.73.1_all.deb
RUN apt-get update
RUN apt-get -y install \
<<<<<<< HEAD
					wget daemon psmisc\
					default-jre
=======
	       wget daemon psmisc\
	       default-jre
>>>>>>> 23f780f77674cffb19a8316034c5ad909c412a33
RUN wget https://pkg.jenkins.io/debian-stable/binary/"$JENKINS_VERSION"
RUN dpkg -i "$JENKINS_VERSION"
COPY docker-entrypoint.sh /usr/local/bin/
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT sh entrypoint.sh && bash
EXPOSE 8080
