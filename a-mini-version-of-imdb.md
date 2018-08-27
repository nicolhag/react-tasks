---
description: ...sort of!
---

# A mini-version of IMDB

The last assignment is mostly up to your self what you want to focus on. Now, use what you have learnt about React to build on the previous assignments and create something cool. As starting help, we supply you with two example directions we think would be fun to implement!

## First example: show cards about each movie

One of us, Kristofer, chose to begin to implement a pretty cool movie app, showing a list of poster, where you can click on each of them and get more information about the movie. Take a look, and click around!

{% embed data="{\"url\":\"https://w67l4467lk.codesandbox.io/345940\",\"type\":\"link\",\"title\":\"React App\",\"icon\":{\"type\":\"icon\",\"url\":\"https://w67l4467lk.codesandbox.io/favicon.ico\",\"aspectRatio\":0}}" %}

## Second example: add a search field or dropdown to filter!

Add a search field or dropdown to filter the list on the `vote_count` or `vote_average` variable in the movie object. An example of how you can easily filter the movie list based on a vote threshold value:

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



