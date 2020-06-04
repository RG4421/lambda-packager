FROM amazonlinux:latest

RUN yum -y groupinstall "Development Tools" \
    && yum -y install git \
    wget \
    automake \
    bzip2-devel \
    libffi-devel \
    libressl-dev \
    openssl-devel \
    postgresql-dev \
    which \
    && yum clean all \
    && wget https://www.python.org/ftp/python/3.6.10/Python-3.6.10.tgz \
    && tar xzf Python-3.6.10.tgz \
    && cd Python-3.6.10 && autoreconf -i && ./configure --enable-optimizations && make altinstall \
    && cd .. \
    && rm Python-3.6.10.tgz \
    && python3.6  -m pip install --upgrade pip

ENV VERSION=3.6

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
CMD /entrypoint.sh
