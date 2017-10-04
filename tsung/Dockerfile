FROM ubuntu:16.04
MAINTAINER Danny Ho <danny.ho@hpe.com>
RUN apt-get update
RUN apt-get install -y \
    gnuplot-nox \
    libtemplate-perl \
    libhtml-template-perl \
    libhtml-template-expr-perl \
    wget \
    make
RUN wget \
    http://packages.erlang-solutions.com/site/esl/esl-erlang/FLAVOUR_1_general/esl-erlang_20.1-1~ubuntu~xenial_amd64.deb
RUN wget \
    http://ppa.launchpad.net/nilarimogard/webupd8/ubuntu/pool/main/w/wxwidgets2.8/libwxbase2.8-0_2.8.12.1+dfsg2-2ubuntu2+1~webupd8~xenial0_amd64.deb
RUN wget \
    http://kr.archive.ubuntu.com/ubuntu/pool/universe/w/wxwidgets3.0/libwxbase3.0-0_3.0.0-2_amd64.deb
RUN dpkg -i libwxbase2.8-0_2.8.12.1+dfsg2-2ubuntu2+1~webupd8~xenial0_amd64.deb
RUN dpkg -i libwxbase3.0-0_3.0.0-2_amd64.deb
RUN apt-get install -y \
    libwxbase3.0-0v5
RUN apt-get install -y apt-utils
RUN dpkg -i esl-erlang_20.1-1~ubuntu~xenial_amd64.deb
RUN wget http://tsung.erlang-projects.org/dist/tsung-1.6.0.tar.gz
RUN tar -xvzf tsung-1.6.0.tar.gz
WORKDIR tsung-1.6.0/
RUN ./configure && make && make install
WORKDIR /
COPY docker-entrypoint.sh /usr/local/bin/
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh
ENTRYPOINT sh entrypoint.sh && bash
