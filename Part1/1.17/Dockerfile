FROM centos:7
ENV container docker
EXPOSE 22
RUN yum -y update && \
    yum -y install ksh.x86_64 vim-enhanced.x86_64 less.x86_64 man-db.x86_64 man-pages.noarch \
                   openssh.x86_64 openssh-clients.x86_64 openssh-server.x86_64 \
                   openssl.x86_64 certmonger.x86_64 && \
    yum clean all && \
    echo "password" | passwd --stdin root && \
    rm -f /run/nologin && \
    mkdir -p mkdir /var/run/sshd && chmod -rx /var/run/sshd && \
    ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' && \
    (cd /lib/systemd/system/sysinit.target.wants/; \
     for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done) && \
    rm -f /lib/systemd/system/multi-user.target.wants/* && \
    rm -f /etc/systemd/system/*.wants/* && \
    rm -f /lib/systemd/system/local-fs.target.wants/* && \
    rm -f /lib/systemd/system/sockets.target.wants/*udev* && \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl* && \
    rm -f /lib/systemd/system/basic.target.wants/* && \
    rm -f /lib/systemd/system/anaconda.target.wants/* && \
    ln -s /lib/systemd/system/sshd.service \
          /etc/systemd/system/multi-user.target.wants/sshd.service && \
    ln -s /lib/systemd/system/systemd-user-sessions.service \
          /etc/systemd/system/multi-user.target.wants/systemd-user-sessions.service
VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]
