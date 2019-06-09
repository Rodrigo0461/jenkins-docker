FROM centos

RUN yum -y install openssh-server

RUN useradd uremote && \
    echo "qwerty" | passwd uremote --stdin && \
    mkdir /home/uremote/.ssh && \
    chmod -R 700 /home/uremote/

COPY remote-key.pub /home/uremote/.ssh/authorized_keys

RUN chown -R uremote:uremote /home/uremote && \
    chmod 600 /home/uremote/.ssh/authorized_keys

RUN /usr/sbin/sshd-keygen > /dev/null 2>&1

CMD /usr/sbin/sshd -D
 
