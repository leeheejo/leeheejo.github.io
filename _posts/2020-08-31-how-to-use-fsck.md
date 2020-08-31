---
title: "[Linux / Ubuntu] How to use fsck: UNEXPECTED INCONSISTENCY: RUN fsck MANUALLY fsck exited with status code 4"
date: 2020-08-31
categories: linux ubuntu
---

리눅스 부팅 시 아래 처럼 에러 발생 

```
/dev/mapper/ubuntu--vg-root: UNEXPECTED INCONSISTENCY: RUN fsck MANUALLY.
fsck exited with status code 4
```

파일시스템에 문제가 발생했고, fsck를 실행하라는 명령어를 출력해주면서 에러가 발생했다. 

```
fsck -y /dev/mapper/ubuntu--vg-root 
```

하고 완료된 후 재부팅하니 정상 부팅되었다. 


# fsck (file system check) 

https://jhnyang.tistory.com/17

리눅스 파일 시스템을 검사/수리 하는 명령어 

(fsck 명령어는 손상된 디렉터리/파일을 수정할 때 임시로 /lost+found 디렉터리에서 작업을 수행 후 완료되면 사라진다.) 

```
fsck [option] 장치명 
```


## 옵션 

-a: 명령 수행에 대한 확인 질문 없이 무조건 수행 (권장하지 않음)

-v: 점검 내역 상세 보기, 자세한 출력 

-y: 모든 응답을 다 yes로 해서 자동으로 실행 (위에서 사용한 옵션) 

-n: 모든 질문에 대한 응답을 no로 취급 

-f: 파일 시스템의 이상 유무에 산관 없이 강제적으로 파일 시스템 체크) 



## 에러코드 


0: No Errors

1: Filesystem errors corrected 

2: System should be rebooted

4: Filesystem error left uncorrected

8: Operational error

16: Usage or syntax error

32: Fsck canceled by user request

128: Shared-library error


### 동작 단계 


단계1: 블록들과 파일 크기 검사

단계2a: 중복된 이름이 있는지 검사

단계2b: 경로명 검사

단계3: 연결성 검사

단계3b: Shadows/ACLs 인증

단계4: 참조 수 검사

단계5: 싸이클 그룹 검사



