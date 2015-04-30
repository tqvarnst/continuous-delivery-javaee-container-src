FROM demo_base

MAINTAINER Thomas Qvarnstrom <tqvarnst@redhat.com>

# Execute system update
RUN yum -y update && yum clean all

# Install packages necessary to run EAP
RUN yum -y install java-1.7.0-openjdk-devel wget && yum clean all

# Create a user and group used to launch processes
# The user ID 1000 is the default for the first "regular" user on Fedora/RHEL,
# so there is a high chance that this ID will be equal to the current user
# making it easier to use volumes (no permission issues)
RUN groupadd -r jboss -g 1000 && useradd -u 1000 -r -g jboss -m -d /opt/jboss -s /sbin/nologin -c "JBoss user" jboss

# Set the working directory to jboss' user home directory
WORKDIR /opt/jboss

# Specify the user which should be used to execute all commands below
USER jboss

# Set the JAVA_HOME and EAP_VERSION variable
ENV JAVA_HOME /usr/lib/jvm/java
ENV EAP_VERSION 6.4.0

# Add JBoss EAP binary
RUN wget -O /tmp/jboss-eap-${EAP_VERSION}.zip http://download.eng.bos.redhat.com/released/JBEAP-6/${EAP_VERSION}/jboss-eap-${EAP_VERSION}.zip

RUN /usr/bin/unzip -q /tmp/jboss-eap-${EAP_VERSION}.zip -d /opt/jboss

RUN mv /opt/jboss/jboss-eap-* /opt/jboss/jboss-eap-${EAP_VERSION} 

RUN /opt/jboss/jboss-eap-${EAP_VERSION}/bin/add-user.sh admin admin-123 --silent

USER root
RUN rm -f /tmp/jboss-eap-${EAP_VERSION}.zip

USER jboss

CMD /opt/jboss/jboss-eap-${EAP_VERSION}/bin/standalone.sh -b 0.0.0.0 -bmanagement 0.0.0.0

