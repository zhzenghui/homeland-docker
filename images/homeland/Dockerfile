# NAME:     homeland/homeland
FROM homeland/base:0.2.2

ENV RAILS_ENV 'production'
ENV HOMELAND_VERSION '2.3.2'

MAINTAINER Jason Lee "https://github.com/huacnlee"

RUN useradd ruby -s /bin/bash -m -U &&\
    mkdir -p /var/www &&\
    cd /var/www &&\
    git clone --branch v$HOMELAND_VERSION https://github.com/ruby-china/homeland.git --depth 1
RUN rm -rf /var/www/homeland/vendor/bundle &&\
    cd /var/www/homeland && bundle install --deployment &&\
    find /var/www/homeland/vendor/bundle -name tmp -type d -exec rm -rf {} + &&\
    chown -R ruby:ruby /var/www

WORKDIR /var/www/homeland
