FROM ubuntu:20.10

RUN sed -i 's/archive/old-releases/g' /etc/apt/sources.list
RUN sed -i '/^deb.*security.ubuntu.com/s/^/#/' /etc/apt/sources.list 

RUN apt-get update && \
apt-get install -y build-essential wget zlib1g-dev libssl-dev

RUN wget https://cdn.openbsd.org/pub/OpenBSD/OpenSSH/portable/openssh-8.3p1.tar.gz && \
tar zxvf openssh-8.3p1.tar.gz
RUN sed -i '3s/8.3/?/' /openssh-8.3p1/version.h
WORKDIR /openssh-8.3p1

RUN ./configure && \
make && \
make install

CMD ["bash"]
