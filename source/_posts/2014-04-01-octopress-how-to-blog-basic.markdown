---
layout: post
title: "Octopress - How to blog (basic)"
date: 2014-04-01 16:26:39 -0300
comments: true
categories: octopress, docsforcoders
---

[documentation]: http://octopress.org/

Mode details? Read [documentation].

### Posts

    # create
    $ bundle exec rake new_post["Octopress - How to blog (basic)"]
    # Creating new post: source/_posts/2014-04-01-octopress-how-to-blog-basic.markdown

    # write
    $ vi source/_posts/2014-04-01-octopress-how-to-blog-basic.markdown

### Pages

    # create with friend url (blog/about)
    $ rake new_page[about]
    # creates /source/about/index.markdown

    # create without friend url (blog/about.html)
    $ rake new_page[about.mardown]
    # creates /source/about.markdown

    # write
    $ vi source/...

### Preview

    $ bundle exec rake preview
    # acess http://localhost:4000

### Deploy

    $ bundle exec rake generate
    $ bundle exec rake deploy
