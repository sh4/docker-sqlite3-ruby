FROM fatherlinux/centos5-base

RUN yum -y install make curl unzip gcc openssl openssl-devel subversion bison zlib zlib-devel

ADD ./build_ruby  /build_ruby
RUN chmod +x /build_ruby
RUN /build_ruby

ADD ./build_sqlite3-ruby /build_sqlite3-ruby
RUN chmod +x /build_sqlite3-ruby
