---
title: "[React] Typo in static class property declaration react/no-typos"
date: 2020-09-03
categories: reactjs
---

Typo in static class property declaration react/no-typos

```
//error
MoviePoster.Prototype = {
    poster: PropTypes.string.isRequired
}
```

MoviePoster.Prototype -> MoviePoster.proptype 

```
//success
MoviePoster.prototype = {
    poster: PropTypes.string.isRequired
}
```
