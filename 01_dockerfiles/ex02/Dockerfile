FROM ruby:latest
RUN apt-get update && apt-get install -y build-essential libpq-dev nodejs sqlite3
RUN gem install rails

ONBUILD COPY app/ /opt/app

# Create a Rail App
ONBUILD RUN bundle install

# Create SQlite databse 
ONBUILD RUN rails db:migrate

# Lance 
# -db: create		// cree database for the current rails env
# -db: schema:load	// load le schema
# -db: seed		// run la db
ONBUILD RUN rails db:setup
