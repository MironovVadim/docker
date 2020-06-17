FROM ruby:2.2

RUN apt-get update -qq && apt-get install -y build-essential && apt-get install -y apt-utils \
&& gem install bson -v '4.2.2' --source 'https://rubygems.org/' \
&& gem install bcrypt -v '3.1.11' --source 'https://rubygems.org/' \
&& gem install bson_ext -v '1.5.1' \
&& gem install puma -v '3.10.0'

ENV APP_HOME /app

RUN mkdir $APP_HOME
WORKDIR $APP_HOME
ADD Gemfile* $APP_HOME/
RUN bundle install
ADD . $APP_HOME

ENV COMMENT_DATABASE_HOST mongodb
ENV COMMENT_DATABASE comments

CMD ["puma"]