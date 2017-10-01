FROM ubuntu:16.04
MAINTAINER Danny Ho <danny.ho@hpe.com>
RUN apt-get update
RUN apt-get install -y \
    erlang \
    gnuplot-nox \
    libtemplate-perl \
    libhtml-template-perl \
    libhtml-template-expr-perl \
    wget \
    make
RUN wget http://tsung.erlang-projects.org/dist/tsung-1.6.0.tar.gz
RUN tar -xvzf tsung-1.6.0.tar.gz
WORKDIR tsung-1.6.0/
RUN ./configure && make && make install
WORKDIR /tsung-1.6.0/examples
COPY docker-entrypoint.sh /usr/local/bin/
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT sh entrypoint.sh && bash
