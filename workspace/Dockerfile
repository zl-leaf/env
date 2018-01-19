FROM phusion/baseimage

RUN apt-get -y update

# php7
RUN apt-get install -y php7.0-cli

# Install nvm (A Node Version Manager)
ARG NODE_VERSION=stable
ENV NODE_VERSION ${NODE_VERSION}
ENV NVM_DIR /root/.nvm
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash && \
    . $NVM_DIR/nvm.sh && nvm install ${NODE_VERSION} && \
    nvm use ${NODE_VERSION} && \
    nvm alias ${NODE_VERSION} && \
    npm install -g gulp bower vue-cli \

# composer
RUN curl -sS https://getcomposer.org/installer | php