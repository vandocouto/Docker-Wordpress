# imagem default
FROM ubuntu:16.04

# Responsavel
MAINTAINER Evandro Couto "vandocouto@gmail.com"

# update e instalação de pacotes
RUN apt-get update && apt-get install python-software-properties software-properties-common -y && \
    add-apt-repository ppa:nginx/stable && \
    apt-get update && apt-get install nginx -y && \
    apt-get install vim passwd ifstat unzip net-tools curl nginx php7.0-fpm php7.0-cli php7.0-gd php7.0-dev php7.0-json php7.0-mysql php7.0-xml php7.0-xmlrpc php7.0-imap php7.0-mbstring php7.0-zip telnet wget openssh-server apt-utils php-redis -y && \
    rm -rf /var/lib/apt/lists/*

# Download do wordpress
WORKDIR /var/www/html
RUN wget https://wordpress.org/latest.zip && \
    unzip latest.zip && \
    chown www-data.www-data -R /var/www/html 

# ajustando o SSH
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key -N '' -y && \
    sed -i 's/PermitRootLogin without-password/#PermitRootLogin without-password/g' /etc/ssh/sshd_config && \
    sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config && \
    echo 'root:root' | chpasswd

# Exportando LANG=C
RUN echo 'export LANG=C' >> /etc/profile

# localtime
RUN rm /etc/localtime && \
    ln -s /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

# mkdir
RUN mkdir /run/php 

# site-available
RUN rm /etc/nginx/sites-available/default && \
    rm /etc/php/7.0/fpm/pool.d/www.conf

# Dir
WORKDIR /

# copy
COPY conf/default 	/etc/nginx/sites-available/
COPY conf/www.conf 	/etc/php/7.0/fpm/pool.d/ 
COPY scripts/start.sh 	/

# start
#ENTRYPOINT ["/start.sh"]

# ports
EXPOSE 80
