FROM centos:centos6
MAINTAINER Takanori Ikeda <orepuri@gmail.com>
LABEL Description="td-agent docker image" Version="1.0"

COPY td.repo /etc/yum.repos.d/

RUN yum -y update && yum install -y td-agent git gcc

# RUN /usr/lib64/fluent/ruby/bin/fluent-gem install fluentd-plugin-webhdfs

RUN mkdir /etc/td-agent/conf.d/
COPY td-agent.conf /etc/td-agent/
COPY conf.d/*.conf /etc/td-agent/conf.d/

EXPOSE 24224
EXPOSE 8888

CMD /usr/sbin/td-agent --log /var/log/td-agent/td-agent.log
