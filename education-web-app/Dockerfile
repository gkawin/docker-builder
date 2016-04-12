
FROM node:5-onbuild

#Create app directory
RUN mkdir -p /usr/src/app
RUN git init .
WORKDIR /usr/src/app

# Install base dependencies (sharp)
RUN apt-get update
RUN apt-get install -y lsb-release software-properties-common
RUN curl -s https://raw.githubusercontent.com/lovell/sharp/master/preinstall.sh | bash -

RUN npm install -g nodemon bower

