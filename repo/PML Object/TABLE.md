---
tags: [PML2, E3D, Report, Database, Data Structure]
aliases: [TABLE Object]
classification: Collection and Report Objects
---

# [[TABLE]]

## 개요
TABLE Object는 원시 데이터를 스프레드시트처럼 표 형식으로 조작할 수 있도록 보관하는 데 사용된다. 각 행(Row)은 기본 키(Primary Key)로 정의된 DBREF를 나타내며, 열(Column)은 연관된 COLUMN Object에 따라 DBREF에 대한 정보를 포함한다. 테이블의 정렬은 열의 순서와 관련 열의 정렬 기준에 따르며, 데이터의 서식 지정은 REPORT Object를 통해 수행된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Table**() | | 생성자 (모든 object 설정을 초기화한다). |
| **Table**(DBREF ARRAY, COLUMN ARRAY) | | Primary Key를 DBREF의 ARRAY로, 열(column)을 COLUMN의 ARRAY로 전달하는 생성자. |
| **Table**(COLLECTION, COLUMNARRAY) | | Primary Key를 COLLECTION으로, 열(column)을 COLUMN의 ARRAY로 전달하는 생성자. |
| **PrimaryKey**(COLLECTION) | | COLLECTION에서 직접 채워지는 사용자 정의 Primary Key. |
| **PrimaryKey**(ARRAY of DBREF) | | 사용자 정의 Primary Key. |
| **Column**(REAL n, COLUMN) | | 테이블의 -n번째 열을 교체한다. |
| **ClearColumns**() | | 테이블의 모든 열을 지운다. |
| **Columns**(COLUMN ARRAY) | | COLUMN Object의 ARRAY로부터 열을 설정한다. |
| **Evaluate**() | | 전체 테이블을 평가한다. |
| **EvaluatePrimaryKey**() | | Primary Key 컬렉션을 재평가한다. |
| **PrimaryKey**() | DBREF ARRAY | 테이블의 Primary Key(테이블 열에 대한 참조 목록)를 반환한다. |
| **Columns**() | COLUMN ARRAY | 열 정의(definitions)를 반환한다. 정렬 시 열의 순서가 중요하다. |
| **Cell**(REAL column, REAL row) | ANY | 지정된 열(column)과 행(row)에 있는 셀의 내용을 반환한다. |
| **Column**(REAL n) | [[ARRAY\|ARRAY Object]] | n번째 열의 내용을 반환한다. |
| **Row**(REAL n) | [[ARRAY\|ARRAY Object]] | n번째 행의 내용을 반환한다. |
| **Cell**(STRING key, DBREF) | ANY | 열 식별자(key)와 DBREF에 해당하는 셀의 내용을 반환한다. |
| **Column**(STRING key) | [[ARRAY\|ARRAY Object]] | key로 식별된 열의 내용을 반환한다. |
| **Row**(DBREF) | [[ARRAY\|ARRAY Object]] | DBREF로 식별된 행의 내용을 반환한다. |