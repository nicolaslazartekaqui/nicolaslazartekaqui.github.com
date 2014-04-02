---
layout: post
title: "Sinatra - Response in JSON"
date: 2014-04-02 00:33:01 -0300
comments: true
categories: sinatra ruby json
---

[Continuing](http://nicolaslazartekaqui.github.io/blog/2014/04/01/sinatra-starting/) with my awesome `sinatra` project. Adding a response in json format.

### Gemfile

    $ vi Gemfile

``` ruby Gemfile
source "https://rubygems.org"

ruby "2.0.0"
gem 'sinatra', '1.1.0'
gem 'json'
```

    $ bundle install

### Coding

    $ vi web.rb

``` ruby web.rb
require 'sinatra'

get '/' do
  erb :index
end

get '/json' do
  content_type :json
  { year: Time.now.year }.to_json
end
```

### Runing

    $ ruby web.rb
    # access localhost:4567/json

### Deploy

    $ git commit -a -m "..."
    $ git push heroku master

__Project__ <br/>
Heroku: http://currentyear.herokuapp.com <br />
Github: https://github.com/nicolaslazartekaqui/currentyear
