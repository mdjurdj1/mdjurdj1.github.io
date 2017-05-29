---
layout: post
title:  A Crash Course on Arrow Functions in React Components!
date:   2017-05-29 14:53:16 +0000
---


Depending on what resource you're using to learn React, React code is going to look *really* different. I often see programmers learning React with older, ES5 based materials creating outdated and clunky looking React components because of it. The truth is, ES6 and beyond make React significantly easier to work with. Let's take a look at a sample component written using old Syntax (if this is familiar to you, it's time to embrace modernity!):

```
class Button extends Component {

  constructor(props) {
	super(props)
	this.state = {
	   clicked: false
	}
	this.handleClick = this.handleclick.bind(this)
	}
	
 handleClick = function() {
    this.setState({
		   clicked: !this.state.clicked
		})
 }
	
  render() {
	  return (
		  <button onClick={this.handleClick()}>Howdy!</button>
		)
	}
}
```

Phew, quite a lot of code going on there for a simple Button component. This is exactly the kind of verbose code that ES6+ React will cut down significantly. See, React is pretty cool, and will automagically bind `this` to the parent component if you use `this` in any method provided by the React API (such as render()! ). See that onClick handler in the render of this component? The `this` here as a context already set because React has bound it for us!

Sadly, if we design our own custom functions outside of render() - like, say, our `handleClick()` function - we have to manually assign it a `this` a context ourselves. This is why we have this constructor mumbo jumbo at the head of our component. We're relying on JavaScript's psuedo-class syntax to properly bind the `this` context of our component instances whenever we instantiate a component. **We want `this` to be scoped to our component.** Let's refactor this button using ES6! (Make sure you've got babel and the transform-class-properties plugin!):

```
class Button extends Component {

  state = { clicked: false }
	
 handleClick = () => {
    this.setState({
		   clicked: !this.state.clicked
		})
 }
	
  render() {
	  return (
		  <button onClick={this.handleClick()}>Howdy!</button>
		)
	}
}
```

Believe it or not, these two button components are the exact same component. Using ES6/7's arrow functions and property initializers, `this` will always point to our component on initialization. So, we no longer need a constructor for our component! Even our initial state can be set without explicitly calling `this`! Inside our custom function `handleClick()`, use of arrow functions will *automatically* bind `this` for us, without the need of that clunky `.bind` line we were using earlier. 

Understanding `this` binding is one of the most complicated parts of working with React (and Javascript frameworks in general), but ES6/7 will largely automate this task for you so you can focus on making cool components! There are many more use cases for ES6/7 syntax in React, but hopefully now you'll never have to explicitly bind your custom functions going forward.
