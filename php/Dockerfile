FROM phpdockerio/php80-fpm:latest
WORKDIR "/srv"

# Fix debconf warnings upon build
ARG DEBIAN_FRONTEND=noninteractive

# Install git
RUN apt-get update \
    && apt-get -y install \
        git 

# Install redis
RUN apt-get update \
    && apt-get -y install \
        redis 

# Install connection utils
RUN apt-get update \
    && apt-get -y install \
        net-tools \
        iputils-ping \
        iproute2 \
        dnsutils \
        traceroute

# Install other stuff
RUN apt-get update \
    && apt-get -y install \ 
        apt-utils \
        vim \
        libcurl3-openssl-dev 

# Install selected extensions
RUN apt-get update \
    && apt-get -y --no-install-recommends install \
        php8.0-memcached \
        php8.0-mysql \
        php8.0-redis \
        php8.0-sqlite3 \
        php8.0-xdebug \
        php8.0-bcmath \
        php8.0-bz2 \
        php8.0-gd \
        php8.0-gmp \
        php8.0-imap \
        php8.0-intl \
        php8.0-soap \
        php8.0-tidy \
        php8.0-xmlrpc \
        php8.0-xsl \
        php8.0-dev \
        php-pear

RUN apt-get clean; rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/*

