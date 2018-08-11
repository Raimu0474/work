FROM ruby:2.5.1

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs wget ca-certificates openssl 
RUN mkdir /app
WORKDIR /app

COPY ./Gemfile /app/Gemfile
COPY ./Gemfile.lock /app/Gemfile.lock

RUN npm install -g yarn
RUN bundle install -j4 --path vendor/bundle

ADD . /app