---
title: "git add 취소하기"
date: 2020-08-20 14:28:28 -0400
categories: git
---

실수로 git add --all를 한 후, 일부 혹은 전체 파일을 제외하고 싶은 경우 

​```
$git add --all
​```

`git reset HEAD [file]` 명령어를 통해 해당 파일을 git add 취소 하거나, 
git reset HEAD (파일명 없이) 전체 파일 git add를 취소할 수 있다.

```
$git reset HEAD [file]
```
