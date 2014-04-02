---
layout: post
title: "Ramaze - Starting"
date: 2014-04-02 00:35:33 -0300
comments: true
categories: ramaze ruby
---

[ramaze]: http://ramaze.net/
[heroku]: http://heroku.com
[github/project]: https://github.com/nicolaslazartekaqui/currentmonth

> Best way to learn? Building.

Buiding a simple application with [ramaze] and deploy in [heroku] to remember what is current month :).

### Ramaze

Using framework generator to create your app.

    $ gem install ramaze
    $ ramaze create currentmonth
    $ bundle install
    $ cd currentmonth

### Removing examples

    $ rm -rf layout public view/index.xhtml controller/main.rb

If we need the files, then we create.

### Coding

    $ vi controller/main.rb

``` ruby controller.rb
class MainController < Controller
  def index
    @month = Time.now.strftime('%B')
  end
end
```

    $ vi view/index.xhtml

``` html
<div>
  #{@month}
</div>
```

Ramaze maps routes using controllers, by default `/` is mapped in `MainController`. Case want a route like `/month` then must be created a controller 'MonthController' or must be specified a route in controller. See the docs by [ramaze] for more info.
### Runing

    $ rake ramaze:start
    # access localhost:7000

### Heroku

    $ git add -A
    $ git commit -a -m "..."
    $ heroku create <APP_NAME>
    $ git push heroku master

__Project__ <br/>
Heroku: http://currentmonth.herokuapp.com <br />
Github: https://github.com/nicolaslazartekaqui/currentmonth
