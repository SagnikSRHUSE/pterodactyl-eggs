FROM mongo:5-focal

LABEL author="Sagnik Sasmal" maintainer="sagnik@sagnik.me"

# Ignore APT warnings about not having a TTY
ENV DEBIAN_FRONTEND noninteractive

# Install Dependencies
RUN apt update -y \
    && apt install -y netcat iproute2 \
    && useradd -d /home/container -m container -s /bin/bash

USER container

ENV USER=container HOME=/home/container

WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh

CMD ["/bin/bash", "/entrypoint.sh"]
