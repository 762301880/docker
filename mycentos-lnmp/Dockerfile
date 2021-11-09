FROM centos:latest
# 设置作者信息
MAINTAINER yaoliuyang<762301880@qq.com>
#  安装vim编辑器&编译工具
RUN yum -y  update \
  && yum -y install vim \
     wget \
  && yum -y install make \
       zlib \
       zlib-devel \
       gcc-c++  \
       libtool \
       openssl \
       openssl-devel
# 安装php 跳过校验整数下载
# 安装依赖
RUN yum -y install libxml2-devel \
     sqlite-devel \
      # 下载源码包
      && wget https://www.php.net/distributions/php-7.4.3.tar.gz --no-check-certificate \
      # 解压 & 进入
      && tar -zxvf  php-7.4.3.tar.gz \
      && cd php-7.4.3 \
      # 配置  --disable-fileinfo
      && ./configure  --prefix=/usr/local/php7.4.3  --disable-fileinfo  --enable-fpm --without-pear  --disable-phar \
      && make \
      && make install \
      && ln -s /usr/local/php7.4.3/bin/php  /usr/bin/php \
      && cp /php-7.4.3/php.ini-development /usr/local/php7.4.3/lib/php.ini \
      && rm -rf /php-7.4.3 \
      && rm -rf /php-7.4.3.tar.gz \