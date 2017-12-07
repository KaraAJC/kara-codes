---
layout: post
title: git commit interpolation
date:  2017-10-31
categories: til technical
tags: git string interpolation
permalink: /til/git-commit-string-interpolation
---

Today, trying to setup a collection of commits that document how to move from using rails `has_secure_password` to using Devise gem, I made this delightful commit:

![bundle install wooot](/pics/git-commit-interpolation.jpg)

In my attempt to quote the command that one should use to make the changes for each step of work, I inadvertedly discovered that a commit message will indeed run the command you give if not appropriately escaped.
