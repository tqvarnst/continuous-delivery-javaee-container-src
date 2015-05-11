FROM rhel7.1

RUN groupadd -r jenkins -g 998 && useradd -u 999 -r -g jenkins -d /home/jenkins -s /bin/bash -c "jenkins" jenkins
RUN mkdir -p /u02/maven/repository
RUN chown -R jenkins:jenkins /u02/maven/repository

VOLUME /u02/maven/repository
