FROM node:10-buster

RUN apt-get update
RUN apt-get install -y firefox-esr

ENV MOZ_FORCE_DISABLE_E10S=true

RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
RUN apt-get install -y ./google-chrome-stable_current_amd64.deb
