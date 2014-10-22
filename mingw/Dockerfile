FROM ubuntu:latest

RUN apt-get update -y && apt-get upgrade -y && apt-get install -y mingw-w64 curl wget make

ADD ./build_ruby  /build_ruby
RUN chmod +x /build_ruby
RUN /build_ruby

#ADD ./build_sqlite3-ruby /build_sqlite3-ruby
#RUN chmod +x /build_sqlite3-ruby

#ADD ./build_msgpack-ruby /build_msgpack-ruby
#RUN chmod +x /build_msgpack-ruby

