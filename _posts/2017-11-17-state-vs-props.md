---
layout: post
title: State V Props
date:  Fri Nov 17 16:33:20 CST 2017
categories: til
tags: tech react
permalink: /til/state-vs-props
---

I found a new resource that helped me better understand the difference between State and Props in React.

> The main responsibility of a Component is to translate raw data into rich HTML. With that in mind, the props and the state together constitute the raw data that the HTML output derives from.


**further explained by the post:**

> #### props
> _props_ (short for _properties_) are a Component's **configuration,** its _options_ if you may. They are received from above and **immutable** as far as the Component receiving them is concerned.
> A Component cannot change its _props,_ but it is responsible for putting together the _props_ of its child Components.

**So when I make a component, I'm setting up HOW props will be used**
```jsx
class Title extends Component

render() {
  return (
    <div className="title">
      <h1>{this.props.firstName}</h1>
      <h2>{this.props.hometown}<h2>
...

```

**Then I use them as I use the component**
```jsx
  ... /* inside App.js, inside it's render function,
      which will be sent to the DOM */
  <Title firstName="Kara" hometown="Denver" />
  ...
```

> #### state
> The _state_ starts with a default value when a Component mounts and then **suffers from mutations in time (mostly generated from user events).** It's a serializable* representation of one point in time—a snapshot.
> A Component manages its own _state_ internally, but—besides setting an initial state—has no business fiddling with the _state_ of its children. You could say the state is **private.**

> \* We didn't say _props_ are also serializable because it's pretty common to pass down callback functions through _props._

#### Changing _props_ and _state_

|  | props | state |
---- | ---- | ----
Can get initial value from parent Component? | Yes | Yes
Can be changed by parent Component? | Yes | No
Can set default values inside Component?* | Yes | Yes
Can change inside Component? | No | Yes
Can set initial value for child Components? | Yes | Yes
Can change in child Components? | Yes | No

> \* Note that both _props_ and _state_ initial values received from parents override default values defined inside a Component.

[Source: State V Props](https://github.com/uberVU/react-guide/blob/master/props-vs-state.md)