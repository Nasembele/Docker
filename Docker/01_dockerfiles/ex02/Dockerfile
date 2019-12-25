FROM ruby

RUN apt-get update -y && apt-get install -y build-essential libpq-dev nodejs sqlite3

ONBUILD COPY app /opt/app
ONBUILD WORKDIR /opt/app

ONBUILD EXPOSE 3000
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed


#docker build -t ft-rails:on-build .
#Docker build -t ft-rails: on-build. - Создаём образ из вашего Dockerfile
#Docker build -t ex02. - Создаём образ из Dockerfile, предоставленного задачей
#docker run -it --rm -p 3000: 3000 ex02 - запускаем созданный образ