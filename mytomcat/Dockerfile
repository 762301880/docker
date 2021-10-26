# 选择镜像
FROM centos:latest
# 设置作者信息
MAINTAINER yaoliuyang<762301880@qq.com>

# 安装wget 下载 环境包
RUN yum -y install vim \
    && yum -y install wget \
    && wget https://mirrors.cnnic.cn/apache/tomcat/tomcat-9/v9.0.54/bin/apache-tomcat-9.0.54.tar.gz \
    && wget https://repo.huaweicloud.com/java/jdk/8u151-b12/jdk-8u151-linux-x64.tar.gz

# 解压文件 && 转移文件到想要的目录 && 删除源文件
RUN tar -zxvf apache-tomcat-9.0.54.tar.gz \
     && mv apache-tomcat-9.0.54 /usr/local/ \
     && tar -zxvf  jdk-8u151-linux-x64.tar.gz \
     && mv jdk1.8.0_151 /usr/local/ \
     && rm -rf /apache-tomcat-9.0.54.tar.gz \
     && rm -rf /jdk-8u151-linux-x64.tar.gz

# 设置环境变量
ENV MYPATH /usr/local
# 设置工作目录 变量是上面设置的环境变量
WORKDIR $MYPATH
# 设置java环境变量
ENV JAVA_HOME /usr/local/jdk1.8.0_151
ENV CLASSPATH  $JAVA_HOME/lib/dt.jar;$JAVA_HOME/lib/tools.jar
# 配置tomcat 目录
ENV CATALINA_HOME /usr/local/apache-tomcat-9.0.54
ENV CATALINA_BASH /usr/local/apache-tomcat-9.0.54
# 保存path
ENV PATH $PATH:$JAVA_HOME/bin:$CATALINA_HOME/lib:$CATALINA_HOME/bin
# 暴露端口
EXPOSE 8080
# 启动并输出日志
CMD /usr/local/apache-tomcat-9.0.54/bin/startup.sh && tail -F /usr/local/apache-tomcat-9.0.54/bin/logs/catalina.out