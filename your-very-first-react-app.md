---
description: This section describes the main constituents of a React application
---

# Your very first React app

## A minimal example, dissected

The snippet below shows a sample`index.js` file, illustrating a minimal example of a complete React application.

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```jsx
import React from "react";
import ReactDOM from "react-dom";


function App() {
  return (
    <div>
      <h1> Hello world! </h1>
    </div>
  );
}

const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Let's dissect it! 

### Part 1: Imports

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```javascript
import React from "react";
import ReactDOM from "react-dom";

```
{% endcode-tabs-item %}
{% endcode-tabs %}

Allright, the first import is needed to access all the React-specific syntaxes in the namespace of this file. An example of this JSX; when we import the `react` -package, the JSX-syntax is understood.

Next, we need to import `ReactDOM`, in order to render our JSX as a part of the [React _virtual_ DOM](https://reactjs.org/docs/faq-internals.html). 

### Part 2: React Component Declaration \([official docs](https://reactjs.org/docs/components-and-props.html#functional-and-class-components)\)

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```jsx
function App() {
  return (
    <div>
      <h1> Hello world! 
</h1>
    </div>
  );
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

So, we need to create a React Component! This is actually nothing worse than creating a good ol' JavaScript function. The two main differences, though, is:   
1. We uppercase the function name   
2. We need to return either _one_ JSX-element \(as here\), or __`null`

{% hint style="info" %}
You can also declare a React Component with the newest JavaScript function declaration called [arrow-functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions):

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```jsx
const App = () => (
    <div>
      <h1> Hello world! </h1>
    </div>
);
```
{% endcode-tabs-item %}
{% endcode-tabs %}

...or even as a JavaScript class definition:

{% code-tabs %}
{% code-tabs-item title="index.js" %}
```jsx
import { Component } from 'react';

...

class App extends Component{
    render(){
        return (
            <div>
                <h1> Hello world! </h1>
            </div>
        );
    }
);
```
{% endcode-tabs-item %}
{% endcode-tabs %}
{% endhint %}

> Remember for later that each React Component should live in a separate file. This makes it reusable and nice!

### Part 3: Render it! \([official docs](https://reactjs.org/docs/rendering-elements.html#rendering-an-element-into-the-dom)\)

```jsx
const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);
```

In order to render our nifty JSX, we need to tell React what to render. The `render`  function from `ReactDOM` takes two arguments; the root-element of your App and what HTML-element to append it to. We have both 💥

## Assignment: Playtime!

The first assignment is to play around with the code we just dissected:

{% embed data="{\"url\":\"https://codesandbox.io/s/wq3j418p9w\",\"type\":\"rich\",\"title\":\"wq3j418p9w - CodeSandbox\",\"description\":\"The online code editor tailored for web applications\",\"icon\":{\"type\":\"icon\",\"url\":\"https://codesandbox.io/favicon.ico\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://codesandbox.io/api/v1/sandboxes/wq3j418p9w/screenshot.png\",\"width\":1200,\"height\":630,\"aspectRatio\":0.525},\"embed\":{\"type\":\"reader\",\"url\":\"https://codesandbox.io/embed/wq3j418p9w\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 50%;\\\"><iframe src=\\\"https://codesandbox.io/embed/wq3j418p9w\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen></iframe></div>\",\"aspectRatio\":2},\"caption\":\"Well, hello there React!\"}" %}

Feel free to alter the code at [https://codesandbox.io/s/wq3j418p9w](https://codesandbox.io/s/wq3j418p9w). 







### 

