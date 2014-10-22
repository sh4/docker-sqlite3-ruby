FROM mizzy/centos-4.8-i386

RUN yum -y install make curl unzip gcc openssl openssl-devel subversion bison zlib zlib-devel

ADD ./build_ruby  /build_ruby
RUN chmod +x /build_ruby
RUN /build_ruby

ADD ./build_sqlite3-ruby /build_sqlite3-ruby
RUN chmod +x /build_sqlite3-ruby

ADD ./build_msgpack-ruby /build_msgpack-ruby
RUN chmod +x /build_msgpack-ruby

