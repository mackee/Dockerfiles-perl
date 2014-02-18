FROM ubuntu:13.10

MAINTAINER mackee

RUN apt-get update
RUN apt-get install -y curl gcc make git

RUN curl https://raw.github.com/tokuhirom/Perl-Build/master/perl-build | perl - -DDEBUGGING=-g 5.18.2 /opt/perl-5.18/

ENV PATH /opt/perl-5.18/bin:$PATH

RUN curl -L http://cpanmin.us | perl - --notest App::cpanminus
