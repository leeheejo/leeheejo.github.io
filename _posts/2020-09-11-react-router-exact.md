---
title: "react-route-dom exact 란?"
date: 2020-09-11
categories: react reactjs
---


```
<Route path='/manage/producer' component={ProducerList}/>
<Route path='/manage/producer/detail' component={ProducerDetails}/>
```

이렇게 설정하고 `/manage/producer/detail`경로를 치니까 자꾸 `/manage/producer`경로로 라우팅 되더라. 

그래서 `/manage/producer` 라우팅 설정하는 부분에 

이 경로와 완전히 일치하는 경우에만 이동하라는 `exact` 설정을 붙여주었다. 

```
<Route exact path='/manage/producer' component={ProducerList}/>
<Route path='/manage/producer/detail' component={ProducerDetails}/>
```

정상동작!
