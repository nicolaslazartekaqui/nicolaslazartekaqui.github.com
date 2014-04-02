---
layout: post
title: "Postgres - How to work with dump"
date: 2013-03-21 13:27
comments: true
categories: postgres, docsforcoders
---

### SQL

#### Exporting

one base

    $ pg_dump -U username dbname -f dumpfile.sql

all bases

    $ pg_dumpall -U username > dumpfile.sql

#### Importing

one base

    $ psql -d dbname -U username -f dumpfile.sql

all bases

    $ psql -U username -f dumpfile.sql
