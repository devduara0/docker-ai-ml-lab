FROM ubuntu:18.04
MAINTAINER InternalLabnet <admin@internal.labnet>
WORKDIR /ai
RUN apt-get update
RUN apt-get -qy install openssh-server python3-pip python3-venv time supervisor 
RUN time pip3 install grpcio==1.28.1
RUN mkdir /var/run/sshd; chmod 755 /var/run/sshd
RUN mkdir /root/.ssh; chown root. /root/.ssh; chmod 700 /root/.ssh
RUN ssh-keygen -A

ADD supervisord.conf /etc/supervisor/supervisord.conf

CMD ["/usr/bin/supervisord"]



