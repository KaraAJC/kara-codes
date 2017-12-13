---
layout: post
title: State Design Pattern
date:  2017-12-12
categories: til
tags: Gang-Of-Four OOP Design-Patterns GOF
permalink: /til/state-design-pattern
---

Today I got to have a fascinating conversation with a senior engineer about the **State Design Pattern**.

The State Pattern, [according to Wikipedia](https://en.wikipedia.org/wiki/State_pattern), is a behavioral software design pattern that implements a state machine in an object-oriented way.

If a given object's behavior shifts quite a bit based on multiple states of being throughout run time, State Pattern may be for you!

You might see the objects methods holding really heavy `if/else` statements, based on the objects' state, and the state pattern lets you extract that logic into a polymorphic, abstract class, that deals with what should happen, based on state, then in your original object, you can just call on that abstract class to return the appropriate action.

Some examples for what I think might be good challenges for the State Pattern to help solve are:

- **Apple Trees** - Trees bear fruit at a certain age, and can do things based on various stages of their life...
- **Game Of Life** - Cells can live or die based on the number of neighbors it has...
- **Delivery** - A delicious snack can be delivered based on it's various stages of being done, there being congruent availability between me and the delivery person... and the open status of the food place.

What are some examples you can think of, or have used the State Pattern on?