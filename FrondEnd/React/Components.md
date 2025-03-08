In React, components are the building blocks of the user interface. Let's break down the different types you mentioned:

### Component
A **Component** in React is a JavaScript class or function that optionally accepts inputs (i.e., properties or `props`) and `returns a React element` that describes how a section of the UI should appear. Components can be defined as classes or functions. Here's a simple example of a class component:

```javascript
import React, { Component } from 'react';

class Greeting extends Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

### PureComponent
- A **PureComponent** is similar to a regular component but with a key difference: it implements `shouldComponentUpdate()` with a shallow prop and state comparison. This means that a `pure component` will only `re-render` if its `props or state have changed`.
- This can help improve performance by preventing unnecessary renders.

```javascript
import React, { PureComponent } from 'react';

class Greeting extends PureComponent {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

## To build Own Pure component
- `shouldComponentUpdate()` : by default it is true but you can redefine with own conditions.
``` JS
shouldComponentUpdate(nextProps) {
	if (condition)
		// should update.
		return true
	// otherwise false.
	return false;
} 
```

### Higher-Order Component (HOC)
A **Higher-Order Component (HOC)** is a function that takes a component and returns a new component. HOCs are used to add additional functionality to existing components. They are a pattern derived from Reacts compositional nature.

```javascript
import React from 'react';

function withGreeting(WrappedComponent) {
  return class extends React.Component {
    render() {
      return (
        <div>
          <h1>Hello!</h1>
          <WrappedComponent {...this.props} />
        </div>
      );
    }
  };
}

// Usage
const EnhancedComponent = withGreeting(SomeComponent);
```

In this example, `withGreeting` is a higher-order component that adds a greeting message to any component it wraps.

I hope this helps clarify the differences between these types of components!