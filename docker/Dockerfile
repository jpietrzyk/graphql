FROM ruby:2.6.3

ENV APP_HOME=/app
ENV GEM_HOME=/bundle
ENV PATH $GEM_HOME/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN mkdir -p $APP_HOME

WORKDIR ${APP_HOME}

RUN apt-get update -qq && apt-get install -y build-essential libxml2-dev libxslt1-dev dumb-init

RUN gem install bundler

RUN bundle config --global path $GEM_HOME
RUN bundle config --global bin $GEM_HOME/bin
RUN bundle config --global frozen 0

ADD . $APP_HOME/
