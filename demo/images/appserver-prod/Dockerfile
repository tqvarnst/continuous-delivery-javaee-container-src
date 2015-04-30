FROM demo_appserverbase

MAINTAINER Thomas Qvarnstrom <tqvarnst@redhat.com>

#ADD ./simpledemo.war /opt/jboss/jboss-eap-${EAP_VERSION}/standalone/deployments/

#RUN sed -i "s/enable-welcome-root=\"true\"/enable-welcome-root=\"false\"/g" /opt/jboss/jboss-eap-${EAP_VERSION}/standalone/configuration/standalone.xml

# Set the Java Opts
ENV EAP_VERSION 6.4.0

ADD ticket-monster.war /opt/jboss/jboss-eap-${EAP_VERSION}/standalone/deployments/ 

