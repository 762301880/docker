FROM php:7.4-fpm
# 更新apt源
#  rm -rf /var/lib/apt/lists/*  解释查看： https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#general-guidelines-and-recommendations
RUN sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list \
           && apt update \
           && apt -y install vim \
           && apt -y install wget \
           && apt -y install git \
           && rm -rf /var/lib/apt/lists/*

## 安装composer-必须要安装php
RUN  wget https://getcomposer.org/download/2.1.9/composer.phar \
     && mv composer.phar /usr/local/bin/composer \
     && cd /usr/local/bin/ \
     && chmod -R 777 /usr/local/bin/composer \
     && composer config -g repo.packagist composer https://mirrors.aliyun.com/composer/