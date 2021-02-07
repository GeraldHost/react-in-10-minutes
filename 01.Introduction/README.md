# 1. Introduction

## What is React

As per their [website](https://reactjs.org/) react is "A library for building user interfaces".

If we dig into that statment a little deeper we can say that React allows you to build complex user interfaces
from smaller isolated pieces of code called "components". These small pieces of code, components, are describing
what elements need to be rendered to the DOM. React also maintains any updates that need to be proccessed by state changes
but more about that later.

## Create React App

As per their [website](https://reactjs.org/docs/create-a-new-react-app.html) "an integrated toolchain".

Again if we dig a little deeper `create-react-app` basically just creates all the tooling boilerplate we need for a React app.
If we were doing it ourselves we would have to write all the configuration ourself. `create-react-app` abstracts this and gives us
a massive head start.

To set up a react app can run: `npx create-react-app my-app`

Then to start the application: `cd my-app` and then run `npm start`.

## ReactDOM

We mentioned previously that React manages updates and rendering of components to the DOM. This is nearly true. In fact the `react`
package itself can be considered more like the manager of all these components whereas ReactDOM is in charge of actually taking those
components and rendering them as DOM elements.

For example if you had this HTML

```html
<div id="root"></div>
```

And this JS

```js
const element = document.getElementById("#root");
ReactDOM.render("foo bar", element);
```

This would result in "foo bar" being rendered into `#root`. So we once this code runs we would end up with:

```html
<div id="root">foo bar</div>
```

ReactDOM can be described as providing an interop between the host environment (the DOM) and `react`. In fact there are other host environments
that we can use such as `react-native` which is used for IOS and Android apps or even `ink` which is used to create CLI tools. For the purpose
of getting to understand React we are going to focus on ReactDOM but we should at least know other host environment abstractions exist.

[Take me to part 02](http://localhost)
