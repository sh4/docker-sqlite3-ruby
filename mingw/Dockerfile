FROM ubuntu:latest

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y mingw-w64 curl wget make zlib1g zlib1g-dev libssl-dev unzip

ADD ./build_ruby  /build_ruby
RUN chmod +x /build_ruby
RUN /build_ruby

RUN /ruby-1.8/bin/gem update --system && \
    /ruby-1.9/bin/gem update --system && \
    /ruby-2.0/bin/gem update --system && \
    /ruby-2.1/bin/gem update --system


RUN /ruby-1.8/bin/gem install rake-compiler && \
    /ruby-1.9/bin/gem install rake-compiler && \
    /ruby-2.0/bin/gem install rake-compiler && \
    /ruby-2.1/bin/gem install rake-compiler

RUN PATH=$PATH:/ruby-1.8/bin rake-compiler cross-ruby VERSION=1.8.7-p374 HOST=i686-w64-mingw32 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-1.9/bin rake-compiler cross-ruby VERSION=1.9.3-p547 HOST=i686-w64-mingw32 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.0/bin rake-compiler cross-ruby VERSION=2.0.0-p576 HOST=i686-w64-mingw32 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.0/bin rake-compiler cross-ruby VERSION=2.0.0-p576 HOST=x86_64-w64-mingw32  EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.1/bin rake-compiler cross-ruby VERSION=2.1.3      HOST=i686-w64-mingw32 EXTS=--without-extensions && \
    PATH=$PATH:/ruby-2.1/bin rake-compiler cross-ruby VERSION=2.1.3      HOST=x86_64-w64-mingw32  EXTS=--without-extensions

ADD ./build_sqlite3-ruby /build_sqlite3-ruby
RUN chmod +x /build_sqlite3-ruby

ADD ./build_msgpack-ruby /build_msgpack-ruby
RUN chmod +x /build_msgpack-ruby

