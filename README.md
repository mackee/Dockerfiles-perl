Dockerfiles-perl
================

Docker images with perl interpreter

- using [Perl-Build](https://github.com/tokuhirom/Perl-Build "Perl-Build")
- installed [App::cpanminus](http://metacpan.org//App::cpanminus "App::cpanminus")

# how to build

  $ git clone https://github.com/mackee/Dockerfiles-perl
  $ cd Dockerfiles-perl
  $ docker build -t mackee/perl:ubuntu-5.18.2 ubuntu-5.18.2
  
# Example

  # your Dockerfile
  
  FROM mackee/perl:ubuntu-5.18.2
  
  RUN git clone <your perl repository>
  
  WORKDIR cpanm --installdeps .
  
  RUN prove -lr
  
  EXPOSE 5000
  
  ENTRYPOINT ["plackup"]
  
  CMD ["-port 5000", "app.psgi"]
