---
description: >-
  It's time to make our app a little more interesting by hooking it up to a
  server!
---

# Connecting to a server

Hopefully, you now have created a `Movie` component, and rendered multiple of them in the `MovieList` component. In order to make the application richer, we need to connect to a API.

## A solution to previous assignment

Please take some minutes to take a look a possible solution at [https://codesandbox.io/s/k9zw217kv3](https://codesandbox.io/s/k9zw217kv3). Here, the components now live in their own files, making reusability easier. 

{% hint style="info" %}
Note the syntax in the end of the component files:

`export default MovieList;`

This is here for us to be able to import it in other files like so:

`import MovieList from './MovieList';`
{% endhint %}

## Class components

But first. In the next assignment, you will get acquainted with the [class components in React](https://reactjs.org/docs/react-component.html). They offer good solutions for a wider range of usages - like calling APIs. Here is the precode for this assignment:

```jsx
class App extends React.Component {
  state = {
    movies: [],
    pending: false
  };

  async componentDidMount() {
    this.setState({ pending: true });
    try {
      const response = await fetch("https://movie-api-zymiraagoi.now.sh");
      const movies = await response.json();
      this.setState({ pending: false, movies });
      console.log("movies", movies);
    } catch (e) {
      // TODO: handle the error!
    }
  }

  render() {
    if (this.state.pending) {
      return <div class="loader">Loading...</div>;
    }
    return (
      <div className="App">
        <MovieList movies={this.state.movies} />
      </div>
    );
  }
}
```

Allright, this may seem like a lot - but we will explain it in bite-size portions. 

### React.Component and the component lifecycle

So, the first part is:

```jsx
class App extends React.Component {
```

This is how you define a class component in React. This makes it possible to add [lifecycle methods](https://reactjs.org/docs/react-component.html#the-component-lifecycle), for example methods that should be run on e.g.:

* ...the first component mount \(the first time the component is injected into the DOM\)
* ...every render
* ...unmounting the component \(essentially leaving the component\)

We can also use lifecycle methods to decide when the component should re-render \(think of re-rendering as updating the HTML at our website\). In this assignment, we are using the lifecycle method `componentDidMount` :

```text
  async componentDidMount() {
```

Here, we define what we want to happen right before rendering our component. And, in this case, this means calling the API to get our data!

### Component state

```jsx
class App extends React.Component {
  state = {
    movies: [],
    pending: false
  };
  ...
}
```

In the beginning of our class component, we have defined a component state. This is the data that only concerns the component itself, and is very powerful in React app development! In the state, we define the variables that can change _inside_ the component. This is so that we can render different things, or render things differently, based on the state \(props mentioned in the previous section can also be used for this\). 

### The render function

In a React class component, you actually only _really_ need one function - the `render` function:

```jsx
 render() {
    if (this.state.pending) {
      return <div class="loader">Loading...</div>;
    }
    return (
      <div className="App">
        <MovieList movies={this.state.movies} />
      </div>
    );
  }
```

In this example, we render differently based on the component _state._ If the state's `pending` variable is sat, we only render a loading-screen \(kindof\). Elsewise, we return our app!

So, in order to change the _state_, we need to set the state, which is what happens in `componentDidMount`:

```jsx
async componentDidMount() {
    this.setState({ pending: true });
    ...
  }
```

This is the React way to change the component's state. Finally, inside `componentDidMount` , the API is called, and the state is set accordingly.

```javascript
try {
    const response = await fetch("https://movie-api-zymiraagoi.now.sh");
    const movies = await response.json();
    this.setState({ pending: false, movies });
    console.log("movies", movies);
} catch (e) {
    // TODO: handle the error!
}
```

## The assignment: connecting the movie component and the API data

This assignment is available at [https://codesandbox.io/s/rmw0m9jjlp](https://codesandbox.io/s/rmw0m9jjlp) 

{% embed data="{\"url\":\"https://codesandbox.io/s/rmw0m9jjlp\",\"type\":\"rich\",\"title\":\"rmw0m9jjlp - CodeSandbox\",\"description\":\"The online code editor tailored for web applications\",\"icon\":{\"type\":\"icon\",\"url\":\"https://codesandbox.io/favicon.ico\",\"aspectRatio\":0},\"thumbnail\":{\"type\":\"thumbnail\",\"url\":\"https://codesandbox.io/api/v1/sandboxes/rmw0m9jjlp/screenshot.png\",\"width\":1200,\"height\":630,\"aspectRatio\":0.525},\"embed\":{\"type\":\"reader\",\"url\":\"https://codesandbox.io/embed/rmw0m9jjlp\",\"html\":\"<div style=\\\"left: 0; width: 100%; height: 0; position: relative; padding-bottom: 50%;\\\"><iframe src=\\\"https://codesandbox.io/embed/rmw0m9jjlp\\\" style=\\\"border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;\\\" allowfullscreen></iframe></div>\",\"aspectRatio\":2},\"caption\":\"With minor alterations, the API data is shown in our app!\"}" %}

### The response

OK, so after adding the API call, the `movies` array is now populated from the server. The array consists of object, looking like the following example:

{% code-tabs %}
{% code-tabs-item title="Example API response" %}
```javascript
{
    "vote_count": 7225,
    "id": 299536,
    "video": false,
    "vote_average": 8.3,
    "title": "Avengers: Infinity War",
    "popularity": 281.682,
    "poster_path": "https://image.tmdb.org/t/p/w500/7WsyChQLEftFiDOVTGkv3hFpyyt.jpg",
    "original_language": "en",
    "original_title": "Avengers: Infinity War",
    "genre_ids": [
        12,
        878,
        14,
        28,
        28
    ],
    "backdrop_path": "https://image.tmdb.org/t/p/w1280/bOGkgRGdhrBYJSLpXaxhXVstddV.jpg",
    "adult": false,
    "overview": "As the Avengers and their allies have continued to protect the world from threats too large for any one hero to handle, a new danger has emerged from the cosmic shadows: Thanos. A despot of intergalactic infamy, his goal is to collect all six Infinity Stones, artifacts of unimaginable power, and use them to inflict his twisted will on all of reality. Everything the Avengers have fought for has led up to this moment - the fate of Earth and existence itself has never been more uncertain.",
    "release_date": "2018-04-25"
},

```
{% endcode-tabs-item %}
{% endcode-tabs %}

As we already have taken care of showing the `title` of the movies from previous assignments, we are already rendering that! Now:

1. Choose 2-3 other variables that you want to show in the `Movie` component \(e.g., `release_date`, `vote_average` and `vote_count`\).
2. Also add an `img` inside the `Movie` component, with the `src` attribute sat to the `poster_path` given from the API.

