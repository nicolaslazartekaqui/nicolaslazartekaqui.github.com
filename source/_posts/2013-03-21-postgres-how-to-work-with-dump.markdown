---
layout: post
title: "Postgres - How to work with dump"
date: 2013-03-21 13:27
comments: true
categories: psql
---

Simple tip.

#### Exporting

To save one specific database in a dumpfiles, just do

    $ pg_dump -U username dbname -f dumpfile.sql

or all databases

    $ pg_dumpall -U username > dumpfile.sql

#### Importing

To import a sql dump in postgres, do

    $ psql -d dbname -U username -f dumpfile.sql

Done, now you can save and recover your database. (:
