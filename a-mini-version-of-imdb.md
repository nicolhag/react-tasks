---
description: ...sort of!
---

# A mini-version of IMDB

The last assignment is mostly up to yourself, and what you would like to focus on. Now, use what you have learnt about React so far this week to build upon the previous assignments and create something cool that excites you - having fun is the greatest way to learn! As a starting aid, we supply you with two examples of directions you can take. We believe that these examples will be fun to implement, and illustrates nicely why dynamic React applications works well to build frontend applications!

## First example: show cards about each movie

One of us, Kristofer, chose to begin to implement a pretty cool movie app, showing a list of posters, where you can click on each of them to get more information about the movie. Take a look at the link below, and click around to get ideas for your own app!

{% embed data="{\"url\":\"https://w67l4467lk.codesandbox.io/\",\"type\":\"link\",\"title\":\"React App\",\"icon\":{\"type\":\"icon\",\"url\":\"https://w67l4467lk.codesandbox.io/favicon.ico\",\"aspectRatio\":0},\"caption\":\"Kristofer\'s Proof of concept\"}" %}

## Second example: add a search field or dropdown to filter!

Add a search field or dropdown to filter the movie list. You may for example filter on the `vote_count` or `vote_average` variable in the movie object. An example of how you can easily filter the movie list based on a _vote threshold value_:

```jsx
function MovieList(props) {
  return (
    <div className="movie-list">
      <h1>Movie list</h1>
      {props.movies
        .filter(movie => movie.vote_average > props.voteThreshold)
        .map(movie => (
          <Movie title={movie.title} length={movie.length} />
      ))}
    </div>
  );
}
```



