# 2. Components

## What are components?

Components are the building blocks of a React application. There are a couple of ways
you can write a component. Class Components and Functional Components. Functional
Components are a more modern approach although you should still spend some time to understand
Class Components because (one) it gives you some useful legacy knowledge about react and (two)
in your day job you will likely come across some legacy React project that uses Class Components
and it's better to be prepared!

As stated previously components are little bite sized chunks that make up and application.
Each component can encapsulate it's styling, functionality and state. It is often a nice testable
unit of code - or at least that is the hope!

Lets take a look at some examples.

### Class Components

```js
class HelloWorld extends React.Component {
  render() {
    return <h1>Hello World!</h1>;
  }
}
```

Class components are ES6 classes that have a `render` method that returns some JSX.

### Functional Components

```js
function HelloWorld() {
  return <h1>Hello World!</h1>;
}
```

Functional components are just normal javascript functions that return JSX.

### What is JSX?

We can't talk about React components without talking about JSX. JSX is kind of like a templating
language that is an extention of Javascript. All React components return JSX which gets rendered as
DOM elements and text nodes. Lets take a look at a couple of examples:

We can interpolate javascript values into JSX by using the `{}` syntax.

```js
const name = "World";
const element = <h1>Hello {name}!</h1>;
```

This element would render as

```html
<h1>Hello World!</h1>
```

We can even interpolate functions that return JSX

```js
const getName = () => {
  return "World";
};
const element = <h1>Hello {getName()}!</h1>;
```

This element would render as

```html
<h1>Hello World!</h1>
```

Any valid JS expression can be embeded in JSX in this way. This includes element attributes. The only
think to note here is that JSX attributes use camelCase. So `tabindex` would become `tabIndex` and `stroke-width`
would become `strokeWidth`. One important change is that `class` becomes `className`.

For example:

```js
const name = "World";
const element = (
  <h1 className="title" title={name}>
    Hello {name}!
  </h1>
);
```

This would render

```html
<h1 class="title" title="World">Hello World!</h1>
```

JSX elements with a lowercase first letter will always represent DOM nodes. `<h1>`, `<div>`, `<span>` etc will all render
their equivilent DOM nodes.

However elements can also represent components if we define them with a capital letter first.

For example if we have this component

```js
function HelloWorld() {
  return <h1>Hello World!</h1>;
}
```

We can use it in our JSX like so:

```js
const element = (
  <div>
    <HelloWorld />
  </div>
);
```

This would render:

```html
<div><h1>Hello World!</h1></div>
```

Any attibutes that we pass into our component JSX element get passed into the component function as what we call `props`.
Props are a single object that gets passed to the component function as the first argument.

For example take our same functional component from before. If we give it an attribute of `name` with a value of "World":

```js
const element = (
  <div>
    <HelloWorld name="World" />
  </div>
);
```

`name` gets passed to our Hello World component in the props object and we can reference it like so:

```js
function HelloWorld(props) {
  return <h1>Hello {props.name}</h1>;
}
```

If our Hello World component was a class based component props are available from `this.props`. Eg:

```js
class HelloWorld extends React.Component {
  render() {
    return <h1>Hello {this.props.name}</h1>;
  }
}
```

### The `Children` Prop

... WIP ...

Okay it feels like we've covered a lot of ground here. There are some additional nueances you will come
across when using JSX and defining components but this is the fundamentals.

[Next step component lifecycle!](http://localhost)
