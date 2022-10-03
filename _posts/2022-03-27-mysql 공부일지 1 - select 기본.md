---
title : mysql 공부일지 1 - select 기본
date : 2022-03-27 00:00:00 +09:00
categories : [mysql]
tags : [mysql]
---

select 문은 데이터베이스 에서 가장 사용 많이 하는 명령어이며 
데이터베이스에서 원하는 데이터를 추출할때 사용하는 명령어이다.

## Mysql 8.0 Select

    SELECT  [ALL  |  DISTINCT  |  DISTINCTROW  ] 
    [HIGH_PRIORITY]  
    [STRAIGHT_JOIN]  
    [SQL_SMALL_RESULT]  [SQL_BIG_RESULT]  [SQL_BUFFER_RESULT]  
    [SQL_NO_CACHE]  [SQL_CALC_FOUND_ROWS]  
    _select_expr_  [,  _select_expr_]  ...  
    [_into_option_]  
    [FROM  _table_references_  
    [PARTITION  _partition_list_]]  
    [WHERE  _where_condition_]  
    [GROUP  BY {_col_name_  |  _expr_  |  _position_},  ...  [WITH  ROLLUP]]  
    [HAVING  _where_condition_]  
    [WINDOW  _window_name_  AS  (_window_spec_)  
	    [,  _window_name_  AS  (_window_spec_)]  ...]  
	[ORDER  BY {_col_name_  |  _expr_  |  _position_} 
	[ASC  |  DESC],  ...  [WITH  ROLLUP]]  
	[LIMIT {[_offset_,]  _row_count_  |  _row_count_  OFFSET  _offset_}]  
	[_into_option_]  
	[FOR {UPDATE  |  SHARE} 
		[OF  _tbl_name_  [,  _tbl_name_]  ...]  
		[NOWAIT  |  SKIP  LOCKED]  
	  |  LOCK  IN  SHARE  MODE]  
	  [_into_option_]
Mysql 8.0 Select 문서 중 부분

<del>뭐라는지 모르겠다</del>

위 문서의 내용을 다음과 같이 자주쓰는 명령어로 줄이면 아래처럼 나타나게 된다.

    SELECT 열 이름 FROM 테이블 이름 WHERE 조건

##SELECT 그리고 FROM

    SELECT * FROM names;
위 명령어로 names 안에있는 모든 데이터를 가져온다는 뜻 (select 에서 * 은 모든것이라는 뜻을 가집니다)

|Name|Gender|
|---|---|
|홍길동|남자|
|철수|남자|
|영희|여자|

mysql에 위 데이터가 있다는 가정하에 아래 명령어를 입력하면 names 테이블 안에 Name 열만 가져올수 있다

     SELECT Name FROM names;

실행 결과


|Name|
|------|
|홍길동|
|철수|
|영희|