---
title: "[React] Hooks"
date: 2020-09-10
categories: react reactjs
---

리액트를 사용해서 개발하던 중 function컴포넌트를 class로 변경하려고 하니까 아래와 같은 에러가 발생했다. (바꾸려고 한 이유는 state를 사용해야해서..) 

```
Error: Invalid hook call. Hooks can only be called inside of the body of a function component. This could happen for one of the following reasons:
1. You might have mismatching versions of React and the renderer (such as React DOM)
2. You might be breaking the Rules of Hooks
3. You might have more than one copy of React in the same app
See https://fb.me/react-invalid-hook-call for tips about how to debug and fix this problem.
```
hook을 찾아보니까 

function 컴포넌트에서도 기존 class에서 사용가능하던 lifecycle과 state를 사용가능하게 하는 것이라고...

더 공부하면 class로 변경하지 않고도 개발할 수 있겠다! 

https://codingbroker.tistory.com/23
