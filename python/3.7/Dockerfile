FROM amazonlinux:latest

RUN yum -y groupinstall "Development Tools" && \
    yum -y install git \
    wget \
    automake \
    bzip2-devel \
    libffi-devel \
    libressl-dev \
    openssl-devel \
    postgresql-dev \
    which \
    && yum clean all \
    && wget https://www.python.org/ftp/python/3.7.7/Python-3.7.7.tgz \
    && tar xzf Python-3.7.7.tgz \
    && cd Python-3.7.7 && autoreconf -i && ./configure --enable-optimizations && make altinstall \
    && cd .. \
    && rm Python-3.7.7.tgz \
    && python3.7 -m pip install --upgrade pip

COPY entrypoint.sh /entrypoint.sh
RUN chmod +x /entrypoint.sh
CMD /entrypoint.sh

