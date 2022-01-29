FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive

# Add user so we don't need sudo
RUN useradd -ms /bin/bash node
RUN passwd -d node
RUN usermod -aG sudo node

# Add basic packages
RUN apt-get update
RUN apt-get install -y sudo curl wget git gnupg

# Install chrome
RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | tee /etc/apt/sources.list.d/google-chrome.list
RUN apt-get update
RUN apt-get install -y google-chrome-stable

# Install node
RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash -
RUN apt-get install -y nodejs

RUN npm install -g yarn
