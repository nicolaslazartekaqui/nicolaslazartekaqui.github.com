---
layout: post
title: "Sinatra - Starting"
date: 2014-04-01 17:26:41 -0300
comments: true
categories: sinatra ruby
---

[sinatra]: http://www.sinatrarb.com
[heroku]: http://heroku.com
[github/project]: https://github.com/nicolaslazartekaqui/currentyear

> Best way to learn? Building.

Buiding a simple application with [sinatra] and deploy in [heroku] to remember what is current year :).

    $ mkdir currentyear
    $ cd currentyear

### Bundler

_Why?_ Why not?

    $ gem install bundler

### Gemfile

    $ vi Gemfile

``` ruby Gemfile
source "https://rubygems.org"

ruby "2.0.0"
gem 'sinatra', '1.1.0'
```

    $ bundle install

### Coding

    $ vi web.rb

``` ruby web.rb
require 'sinatra'

get '/' do
  "#{Time.now.year}"
end
```

### Runing

    $ ruby web.rb
    # access localhost:4567

### ERB

    $ vi web.rb

``` ruby web.rb
require 'sinatra'

get '/' do
  erb :index
end
```

    $ mkdir views
    $ vi views/index.erb

``` erb views/index.erb
<div>
  <%= Time.now.year %>
</div>
```

### Heroku

    $ vi Procfile

``` bash Procfile
web: bundle exec ruby web.rb -p $PORT
```

    $ git add -A
    $ git commit -a -m "..."
    $ heroku create <APP_NAME>
    $ git push heroku master

__Project__ <br/>
Heroku: http://currentyear.herokuapp.com <br />
Github: https://github.com/nicolaslazartekaqui/currentyear
