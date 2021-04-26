FROM ubuntu
WORKDIR /usr/app

# Enviroment prepare tzdata apt-utils
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y tzdata apt-utils 2>&1 | \
    grep -v "^debconf: delaying package configuration, since apt-utils.*"

# Install ruby and rbenv
RUN apt-get -y install ruby-full
RUN apt-get -y install rbenv

# Fix libssl
RUN echo "deb http://security.ubuntu.com/ubuntu bionic-security main" >> /etc/apt/sources.list
RUN apt-get -y update && apt-cache policy libssl1.0-dev
RUN apt-get -y install libssl1.0-dev shared-mime-info

# Rbenv install ruby and global
RUN rbenv install 2.3.4
RUN rbenv global 2.3.4

# Set PATH
RUN export PATH="$HOME/.rbenv/bin:$PATH"
RUN eval "$(rbenv init -)"
RUN /bin/bash -c "source /root/.bashrc"

# Install dependencies
RUN gem install faraday -v 1.0.1
RUN gem install launchy -v 2.4.3

#Install
RUN gem install opencode_theme --force
