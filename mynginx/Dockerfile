FROM nginx
# 更新apt源
#  rm -rf /var/lib/apt/lists/*  解释查看： https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#general-guidelines-and-recommendations
RUN sed -i "s@http://deb.debian.org@http://mirrors.aliyun.com@g" /etc/apt/sources.list \
           && apt update \
           && apt -y install vim \
           && apt -y install wget \
           && apt -y install git \
           && rm -rf /var/lib/apt/lists/*

