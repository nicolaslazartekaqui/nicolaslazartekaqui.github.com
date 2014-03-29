---
layout: post
title: "Ruby - Solving error to install gem rmagick in debian"
date: 2013-03-21 12:58
comments: true
categories: ruby rubygems debian rmagick
---

Trying to install the rmagic gem I received this error

    $ gem install rmagick -v '2.13.2'

<!-- more -->

``` bash
Installing rmagick (2.13.2) with native extensions 
Gem::Installer::ExtensionBuildError: ERROR: Failed to build gem native extension.

        /home/nicolas/.rbenv/versions/1.9.3-p0/bin/ruby extconf.rb 
checking for Ruby version >= 1.8.5... yes
checking for /usr/bin/gcc... yes
checking for Magick-config... no
Can't install RMagick 2.13.2. Can't find Magick-config in /home/nicolas/.rbenv/versions/1.9.3-p0/bin:/usr/lib/rbenv/libexec:/home/nicolas/.rbenv/plugins/ruby-build/bin:/home/nicolas/.rbenv/shims:/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:/home/nicolas/bin:/usr/local/java/:/home/nicolas/bin:/usr/local/java/:/home/nicolas/bin:/usr/local/java/jre1.7.0_04:/home/nicolas/bin:/usr/local/java/jre1.7.0_04:/home/nicolas/bin:/usr/local/java/jre1.7.0_05:/home/nicolas/bin:/usr/local/java/jre1.7.0_05

*** extconf.rb failed ***
Could not create Makefile due to some reason, probably lack of
necessary libraries and/or headers.  Check the mkmf.log file for more
details.  You may need configuration options.

Provided configuration options:
  --with-opt-dir
  --without-opt-dir
  --with-opt-include
  --without-opt-include=${opt-dir}/include
  --with-opt-lib
  --without-opt-lib=${opt-dir}/lib
  --with-make-prog
  --without-make-prog
  --srcdir=.
  --curdir
  --ruby=/home/nicolas/.rbenv/versions/1.9.3-p0/bin/ruby


Gem files will remain installed in /home/nicolas/.rbenv/versions/1.9.3-p0/lib/ruby/gems/1.9.1/gems/rmagick-2.13.2 for inspection.
Results logged to /home/nicolas/.rbenv/versions/1.9.3-p0/lib/ruby/gems/1.9.1/gems/rmagick-2.13.2/ext/RMagick/gem_make.out
An error occurred while installing rmagick (2.13.2), and Bundler cannot continue.
Make sure that `gem install rmagick -v '2.13.2'` succeeds before bundling.
```

This error occurs because of missing the necessary library to compile the rmagick. In Debian (I use SID/UNSTABLE version) to fix this error you must install the library `libmagickwand-dev`.

    $ sudo aptitude install libmagickwand-dev

Done, now you can install the gem rmagick and continue working happy. (:
