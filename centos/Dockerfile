FROM centos

RUN yum -y install openssh-server

RUN useradd uremote && \
    echo "qwerty" | passwd uremote --stdin && \
    mkdir /home/uremote/.ssh && \
    chmod -R 700 /home/uremote/

RUN chown -R uremote:uremote /home/uremote 

RUN /usr/sbin/sshd-keygen > /dev/null 2>&1

CMD /usr/sbin/sshd -D
 
