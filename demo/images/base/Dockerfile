FROM centos:centos7

MAINTAINER Thomas Qvarnstrom <tqvarnst@redhat.com>

# Execute system update
RUN yum -y update && yum clean all

# Install packages necessary to run EAP
RUN yum -y install net-tools xmlstarlet saxon augeas bsdtar unzip procps-ng && yum clean all
