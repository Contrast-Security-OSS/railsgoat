FROM ruby:2.6.5@sha256:651078e89471c30567685dce4caa321adf1f846b353e05c327b55d76a84acc50
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN mkdir /myapp
WORKDIR /myapp
ADD Gemfile /myapp/Gemfile
ADD Gemfile.lock /myapp/Gemfile.lock
RUN bundle install --with=openshift
ADD . /myapp
RUN chgrp -R 0 /myapp \
  && chmod -R g+rwX /myapp