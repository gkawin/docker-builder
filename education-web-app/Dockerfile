
FROM node:5-onbuild

#Create app directory
RUN mkdir -p /usr/src/app
RUN git init .
WORKDIR /usr/src/app

# Install base dependencies (sharp)
RUN apt-get update
RUN apt-get install -y lsb-release software-properties-common
RUN curl -s https://raw.githubusercontent.com/lovell/sharp/master/preinstall.sh | bash -

# Install software 
RUN apt-get install -y git
# Make ssh dir
RUN mkdir /root/.ssh/

# Copy over private key, and set permissions
ADD id_rsa /root/.ssh/id_rsa

# Create known_hosts
RUN touch /root/.ssh/known_hosts
# Add bitbuckets key
RUN ssh-keyscan github.com >> /root/.ssh/known_hosts

# Clone the conf files into the docker container
RUN git clone git@github.com:gkawin/edu-game.git education-web-app
