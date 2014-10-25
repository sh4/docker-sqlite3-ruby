FROM ubuntu:latest

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y mingw-w64 curl wget make zlib1g zlib1g-dev libssl-dev 

ADD ./build_ruby  /build_ruby
RUN chmod +x /build_ruby
RUN /build_ruby

RUN /ruby-1.8/bin/gem install rake-compiler && \
    /ruby-1.9/bin/gem install rake-compiler && \
    /ruby-2.0/bin/gem install rake-compiler && \
    /ruby-2.1/bin/gem install rake-compiler

RUN PATH=$PATH:/ruby-1.8/bin rake-compiler cross-ruby VERSION=1.8.7-p374 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-1.9/bin rake-compiler cross-ruby VERSION=1.9.3-p547 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.0/bin rake-compiler cross-ruby VERSION=2.0.0-p576 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.1/bin rake-compiler cross-ruby VERSION=2.1.3 EXTS=--without-extensions

RUN apt-get install -y unzip

#ADD ./build_sqlite3-ruby /build_sqlite3-ruby
#RUN chmod +x /build_sqlite3-ruby

#ADD ./build_msgpack-ruby /build_msgpack-ruby
#RUN chmod +x /build_msgpack-ruby

