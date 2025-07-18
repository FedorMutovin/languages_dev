# Languages DEV
## Docker for Development

Inspired by: [Ruby on Whales: Dockerizing Ruby and Rails development](https://evilmartians.com/chronicles/ruby-on-whales-docker-for-ruby-rails-development).

### Installation

- Docker installed.
- Ruby installed(to install `dip` gem)

For MacOS just use the [official app](https://docs.docker.com/engine/installation/mac/).

- [`dip`](https://github.com/bibendi/dip) installed.

You can install `dip` as Ruby gem:

```sh
gem install dip
```

### Provisioning

When using Dip it could be done with a single command:

```sh
dip provision
```

### Running

```sh
dip rails s
```

### Developing with Dip

#### Useful commands

```sh
# run rails console
dip rails c

# run rails server with debugging capabilities (i.e., `debugger` would work)
dip rails s

# or run the while web app (with all the dependencies)
dip up web

# run migrations
dip rails db:migrate

# pass env variables into application
dip VERSION=20100905201547 rails db:migrate:down

# simply launch bash within app directory (with dependencies up)
dip runner

# execute an arbitrary command via Bash
dip bash -c 'ls -al tmp/cache'

# Additional commands

# update gems or packages
dip bundle install

# run psql console
dip psql

# run tests
# TIP: `dip rspec` is already auto prefixed with `RAILS_ENV=test`
dip rspec spec/path/to/single/test.rb:23

# shutdown all containers
dip down
```

#### Development flow

Another way is to run `dip <smth>` for every interaction. If you prefer this way and use ZSH, you can reduce the typing
by integrating `dip` into your session:

```sh
$ dip console | source /dev/stdin
# no `dip` prefix is required anymore!
$ rails c
Loading development environment (Rails 7.0.1)
pry>
```
