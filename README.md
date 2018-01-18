# docker-ruby-node
Docker image for running ruby with nodejs (in example ruby on rails)

## Example dockerfile
```
FROM bond/ruby-node
RUN mkdir /myapp
WORKDIR /myapp
COPY Gemfile /myapp/
COPY Gemfile.lock /myapp/
COPY package.json /myapp/
COPY yarn.lock /myapp/
RUN bundle install # for development: --without production
RUN bundle exec rails webpack:install
RUN yarn install
```
