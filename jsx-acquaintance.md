---
description: An assignment about JSX and passing props to your components!
---

# Using JSX and props

Allright, so we have already seen some JSX in the example at the previous page. Now, it is time to utilize the power of JSX! The official React documentation describes JSX very well [here](https://reactjs.org/docs/introducing-jsx.html). Feel free to read through this part of the docs first! 

## The concept of Props

Allright, so head over to [https://codesandbox.io/s/k0zo325kk7](https://codesandbox.io/s/k0zo325kk7) for the next assignment. You can start now, or read through this page first - your choice. Now, we want to use the React concept of `props` . You can think of props as arguments that you can give to a function: in JavaScript this may for example be an `object`, an `array`, `null`, or even a `function` \(!\). Here, the [components and props](https://reactjs.org/docs/components-and-props.html) will be useful. All of our props will be available through the `props` parameter: 

```jsx
function Movie(props) {
  console.log('movies', props.movies);
  return null;
}

...

const movies = [{
  title: 'Shawshank Redemption'
}];

<MovieList movies={movies} />
```

{% hint style="info" %}
#### Did you know? 

After the new JavaScript standard from 2015 - ES6 - we no longer need to declare variables in the global namespace, or with `var`.  New syntax lets us indicate if we have a constant or a variable:  
  
`const a = "foo";`

`let a = "bar";`

More about this can be found here \(beware of Norwegian\): [`https://johhorn.gitbooks.io/web-intro/05-javascript/01-variabler.html`](https://johhorn.gitbooks.io/web-intro/05-javascript/01-variabler.html)\`\`
{% endhint %}

## Decorating your components with "built-in" props

In [this CodeSandbox assignment](https://codesandbox.io/s/k0zo325kk7), note that we use `className` , rather than `class` to set a class to our div:

```jsx
return (
    <div className="movie-list">
        ...
    </div>
)
```

This is an example of the React team's strategy for naming HTML attributes. Although they have good reasons for choosing this syntax, it's pretty easy do get these wrong the first times. Read more about the reasoning [here](https://reactjs.org/docs/dom-elements.html#classname). Another common pitfall is when applying styles directly to the element: 

```jsx
return (
    <div style={{marginTop: '2rem', backgroundColor: 'blue'}}>
        ...
    </div>
)
```

Remember to ask for help!

## Reusability

> Components let you split the UI into independent, reusable pieces, and think about each piece in isolation. - Official React documentation

React components are all about reusability, and that's what this assignment tries to encapsulate. When splitting up our code into components, we can easily set them together - like building blocks!  

