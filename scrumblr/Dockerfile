FROM node:latest

RUN apt-get update && apt-get install -y unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN cd /tmp \
    && wget https://github.com/aliasaria/scrumblr/archive/master.zip \
    && unzip master.zip \
    && rm master.zip \
    && mv scrumblr-master /srv/scrumblr \
    && cd /srv/scrumblr \
    && npm install

WORKDIR /srv/scrumblr
ENTRYPOINT ["node", "server.js", "--port", "80", "--redis", "redis"]
