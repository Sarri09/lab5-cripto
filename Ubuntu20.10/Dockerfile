FROM ubuntu:20.10

RUN sed -i 's/archive/old-releases/g' /etc/apt/sources.list
RUN sed -i '/^deb.*security.ubuntu.com/s/^/#/' /etc/apt/sources.list

RUN apt-get update && apt-get install -y sudo net-tools openssh-client tshark

RUN mkdir -p /run/sshd

RUN useradd -m -s /bin/bash test && echo "test:test" | chpasswd

RUN apt-get install -y openssh-server

RUN groupadd -g 999 wireshark && usermod -aG wireshark test
RUN chgrp wireshark /usr/bin/dumpcap && chmod o+x /usr/bin/dumpcap

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]

