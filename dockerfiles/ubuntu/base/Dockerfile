FROM ubuntu
#indicamos el timezone
ARG USUARIO
ARG PASSWD
ARG TZ

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# COPY ./ub-base.sh /root
# COPY ./id_rsa.pub /root

COPY ./start.sh /root
COPY ./id_rsa.pub /root
RUN chmod +x /root/start.sh
RUN mkdir /var/logs

RUN apt update && apt install -yq --no-install-recommends \
    apt-utils \
    wget \ 
    curl \ 
    git \
    nano \ 
    tree \
    net-tools \ 
    iputils-ping \
    sudo \ 
    openssh-server \ 
    openssh-client \
    unzip \
    dos2unix \ 
    expect \
    python3

RUN dos2unix /root/start.sh 
ENTRYPOINT [ "/root/start.sh" ]