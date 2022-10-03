---
title : mysql 공부일지 2 - select where절
date : 2022-03-31 00:00:00 +09:00
categories : [mysql]
tags : [mysql]
---
결과

|Name|Gender|Age|
|---|---|---|
|홍길동|남자|21|

#관계 연산자 사용하기

나이가 20이상만 출력하려면 아래 명령어를 쓴다

```sql
SELECT * FROM names WHERE Name >= 20;
```

결과

|Name|Gender|Age|
|---|---|---|
|홍길동|남자|21|
|철수|남자|24|