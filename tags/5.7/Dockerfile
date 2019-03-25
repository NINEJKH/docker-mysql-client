FROM debian:stretch-slim

ARG DEBIAN_FRONTEND=noninteractive

ENTRYPOINT ["mysql"]

RUN apt-get -qq update && \
    apt-get -y -qq install \
        curl \
        gnupg

RUN while ! apt-key adv --keyserver hkps://peegeepee.com:443 --recv-keys 5072E1F5; do sleep 3; done && \
    printf "deb http://repo.mysql.com/apt/debian/ stretch mysql-5.7\n" | tee /etc/apt/sources.list.d/mysql.list && \
    apt-get -qq update && \
    apt-get -y -qq install mysql-client
