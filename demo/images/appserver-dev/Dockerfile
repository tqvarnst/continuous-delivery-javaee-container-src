FROM demo_appserverbase

MAINTAINER Thomas Qvarnstrom <tqvarnst@redhat.com>

# Set the Java Opts
ENV JAVA_OPTS -client -XX:+TieredCompilation -XX:TieredStopAtLevel=1 -Xverify:none -Xms128m -Xmx256m -Dorg.apache.tomcat.util.LOW_MEMORY=true -XX:+UseCompressedOops -XX:+AggressiveOpts -XX:+DisableExplicitGC -Djava.net.preferIPv4Stack=true

ENV PRESERVE_JAVA_OPTS true


