FROM ruby:2.7.0

RUN apt-get update &&\
    apt-get install -y git vim sqlite3 &&\
    rm -rf /var/lib/apt/lists/*

RUN gem update --system 3.0.4 &&\
    gem install bundler -v '2.1.2'

WORKDIR /usr/src/app/alpha-blog

COPY . .

ENV BUNDLER_VERSION 2.1.2

RUN bundle update &&\
    bundle install &&\
    rails db:setup &&\
    rails db:migrate

EXPOSE 3000

CMD ["rails", "server", "-b", "0.0.0.0"]   



