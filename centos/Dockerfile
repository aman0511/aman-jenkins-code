from centos

run yum -y install openssh-server openssh-clients

run useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \
    mkdir /home/remote_user/.ssh && \
    chmod 700 /home/remote_user/.ssh

copy remote-key.pub /home/remote_user/.ssh/authorized_keys

run chown remote_user:remote_user -R /home/remote_user/.ssh/authorized_keys && \
    chmod 600 /home/remote_user/.ssh/authorized_keys

run /usr/sbin/sshd-keygen

cmd /usr/sbin/sshd -D
