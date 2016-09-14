FROM debian:8.5


# 1. Set timezone

RUN set -x \
    && rm -f /etc/localtime \
    && ln -s /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime


# 2. Copy .bashrc

COPY bashrc /root/.bashrc


# 3. Install Nano

RUN set -x \
    && apt-get update \
    && apt-get install --yes \
                      nano


# 4. Install Oracle JDK 8

COPY webupd8team-java.list /etc/apt/sources.list.d/webupd8team-java.list

RUN set -x \
    && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys EEA14886 \
    && echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections \
    && apt-get update \
    && apt-get install --yes \
                      oracle-java8-installer \
                      oracle-java8-set-default


# 5. Delete apt list files

RUN set -x \
    && rm -rf /var/lib/apt/lists/*
