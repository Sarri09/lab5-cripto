FROM ubuntu:20.10

RUN sed -i 's/archive/old-releases/g' /etc/apt/sources.list
RUN sed -i '/^deb.*security.ubuntu.com/s/^/#/' /etc/apt/sources.list 

RUN apt update && apt install -y sudo net-tools openssh-client

RUN useradd -m -s /bin/bash test && echo "test:test" | chpasswd

RUN apt-get install -y openssh-server

# RUN apt-get install -y wireshark tshark

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
