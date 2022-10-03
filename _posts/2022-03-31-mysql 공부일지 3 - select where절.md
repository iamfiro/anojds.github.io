---
title : mysql 공부일지 3 - select where절
date : 2022-03-31 00:00:03 +09:00
categories : [mysql]
tags : [mysql]
---
## 중복 데이터 제거

만약 출력 데이터에 중복이 있다면

**DISTINCT** 을 사용하여 중복 데이터를 제거 할수 있다.


```sql
SELECT DISTINCT Name FROM names;
```

<br>

## 출력 개수 제한

데이터를 출력할때 출력 개수를 조절해야할때가 있을수 있다

출력 데이터를 조절할때는 **LIMIT** 을 사용하면 된다

```sql
SELECT Name FROM names LIMIT 시작, 개수
```

예시:

```sql
SELECT Name FROM names LIMIT 4,2
```