FROM ruby:2.7

RUN bundle config --global frozen 1

WORKDIR /Users/emolter/emolter.github.io

# prepare to install ruby packages into container
COPY Gemfile Gemfile.lock minimal-mistakes-jekyll.gemspec ./

RUN bundle install

VOLUME /Users/emolter/emolter.github.io

EXPOSE 4000

CMD ["jekyll", "serve"]