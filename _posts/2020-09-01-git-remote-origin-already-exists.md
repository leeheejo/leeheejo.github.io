---
title: "fatal: remote origin already exists."
date: 2020-09-01
categories: git
---

프로젝트를 압축파일로 전달 받은 후, 

이를 깃에 올리려고 하니까 깃에서 아래와 같은 에러가 발생했다. 

```
fatal: remote origin already exists.
```

아마 이전에 보내주신 분의 깃이 연결되어 있는 듯 했다. 

내가 해야할 것은 이전 저장소의 연결을 끊고, 새로운 저장소에 연결하기.


1. 이전 저장소 연결 끊기
```
git remote rm origin
```

2. 새로운 저장소 연결하기 
```
git remote add origin https://(저장소주소).git
```

