FROM centos

RUN yum -y install openssh-server

RUN useradd uremote && \
    echo "qwerty" | passwd uremote --stdin && \
    mkdir /home/uremote/.ssh && \
    chmod -R 700 /home/uremote/

RUN chown -R uremote:uremote /home/uremote 

RUN /usr/sbin/sshd-keygen > /dev/null 2>&1

RUN yum -y install mysql

RUN yum -y install epel-release && \
    yum -y install python-pip && \
    pip install awscli

CMD /usr/sbin/sshd -D
 
