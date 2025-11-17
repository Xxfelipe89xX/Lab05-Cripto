FROM ubuntu:22.10

RUN sed -i 's/archive.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list && \
    sed -i 's/security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list && \
    apt-get update && \
    apt-get install -y openssh-client openssh-server && \
    rm -rf /var/lib/apt/lists/*

RUN useradd -m prueba && echo 'prueba:prueba' | chpasswd
WORKDIR /home/prueba
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
