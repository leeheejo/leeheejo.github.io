---
title: "[React] Typo in static class property declaration react/no-typos"
date: 2020-09-03
categories: reactjs
---

Typo in static class property declaration react/no-typos

```
//error
MoviePoster.PropTypes = {
    poster: PropTypes.string.isRequired
}
```

MoviePoster.PropTypes -> MoviePoster.propTypes 

```
//success
MoviePoster.propTypes = {
    poster: PropTypes.string.isRequired
}
```
