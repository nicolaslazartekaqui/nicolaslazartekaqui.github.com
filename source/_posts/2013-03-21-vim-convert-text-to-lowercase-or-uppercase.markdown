---
layout: post
title: "Vim - Convert text to lowercase or uppercase"
date: 2013-03-21 13:34
comments: true
categories: vim
---

To convert all text to lowercase in vim do

    ggVGu

or uppercase

    ggVGU

look at the command `ggVG` is used to select all the text if you want you can select the text and use `U` or `u` to convert what was selected to uppercase or lowercase.

If you want use this function in search/replace, do this to lowercase (example)

    :%s/[A-Z]/\L&/g

or to uppercase (example)

    :%s/[A-Z]/\U&/g

Or if you want use this function in character, you can switch case doing this in character

    ~
