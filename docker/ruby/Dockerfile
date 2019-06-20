FROM ruby:2.5-alpine

RUN bundle config --global frozen 1
RUN apk add --no-cache git bash
RUN gem install cfn-nag
