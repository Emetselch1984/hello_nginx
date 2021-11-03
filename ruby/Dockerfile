FROM ruby:3.0

# 必要なパッケージのインストール
RUN apt-get update -qq && \
 apt-get install -y build-essential libpq-dev
# yarnのインストール
RUN apt-get update && apt-get install -y curl apt-transport-https wget && \
 curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
 echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
 apt-get update && apt-get install -y yarn
# Nodeのインストール
RUN apt-get install nodejs
RUN mkdir -p tmp/sockets
RUN mkdir /app
RUN cd /app
WORKDIR /app
COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock
RUN bundle install
#RUN gem install bundler
COPY ./hello_nginx/ /app




EXPOSE 3000
# ==========ここまで追加する==========

# 実行したいコマンド

#docker-compose run --no-deps rails rails new . --force -d mysql