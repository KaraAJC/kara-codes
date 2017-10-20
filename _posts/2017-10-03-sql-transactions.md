---
layout: post
title: SQL Transactions
date:   2017-10-03 09:55:30 -0500
categories:til
tags: til hashrocket sql postgres db
permalink: /til/sql-transactions
---

ACID, Y'ALL!!
Today, we had Hashrocket do a day-long workshop about SQL, and discussed Transactions. Transactions have four qualities:
Atomicity - a series of **database** operations such that either all occur, or nothing occurs.
Consistency - start in a valid state, end in a valid state
Isolation - what do others see of the WIP? the more isolation the better.
Durability - when the DB commits, it's persisted to a permanent source.