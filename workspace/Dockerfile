FROM phusion/baseimage

RUN apt-get -y update

# php7
RUN apt-get install -y php7.0-cli && \
    apt-get install -y php7.0-common \
        php7.0-curl \
        php7.0-intl \
        php7.0-json \
        php7.0-xml \
        php7.0-mbstring \
        php7.0-mcrypt \
        php7.0-mysql \
        php7.0-pgsql \
        php7.0-sqlite \
        php7.0-sqlite3 \
        php7.0-zip \
        php7.0-bcmath \
        php7.0-gd \
        php7.0-dev \
        pkg-config \
        libcurl4-openssl-dev \
        libedit-dev \
        libssl-dev \
        libxml2-dev \
        xz-utils \
        git \
        curl \
        vim \
    && apt-get clean

# Install nvm (A Node Version Manager)
ARG NODE_VERSION=stable
ENV NODE_VERSION ${NODE_VERSION}
ENV NVM_DIR /root/.nvm
RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash && \
    . $NVM_DIR/nvm.sh && nvm install ${NODE_VERSION} && \
    nvm use ${NODE_VERSION} && \
    nvm alias ${NODE_VERSION} && \
    npm install -g gulp bower vue-cli

# composer
RUN curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer

# bash
RUN echo "export TERM=xterm-256color" >> ~/.bashrc