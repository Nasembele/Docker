FROM ruby

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - && \
    echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list && \
    apt update && apt install build-essential sqlite3 libpq-dev nodejs yarn -y
    
ONBUILD COPY app /opt/app
ONBUILD WORKDIR opt/app
ONBUILD RUN yarn install --check-files 
ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate 


# docker build -t ft-rails:on-build ./ft-rails
# docker build -t ex02:test .
# docker run --rm -it -p 3000:3000 ex02:test
#
# https://github.com/mhartl/sample_app_6th_ed
# https://yarnpkg.com/en/docs/install#debian-stable:wq
