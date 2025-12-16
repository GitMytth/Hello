FROM ubuntu:20.04

# Установка зависимостей (SSH, Ansible, Docker CLI, Java)
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y openssh-server ansible docker.io openjdk-11-jdk curl nano

# Настройка SSH
RUN mkdir /var/run/sshd
RUN echo 'root:password' | chpasswd
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# Создание рабочей директории
RUN mkdir -p /opt/app

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]