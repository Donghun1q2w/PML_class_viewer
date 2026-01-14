---
tags: [PML2, E3D, Collection, Database, Search]
aliases: [COLLECTION Object]
classification: Collection and Report Objects
---

# [[COLLECTION]]

## 개요
컬렉션(Collection) 객체는 선택 필터(표현식 객체), 제한적 검색 요소 및 범위 목록을 사용하여 시스템에서 데이터베이스 요소를 추출하는 데 사용된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Collection**() | | 생성자 (모든 객체 설정을 초기화한다). |
| **Scope** (COLLECTION) | | 현재 범위 목록을 비우고 전달된 COLLECTION을 현재 범위로 만든다. |
| **Scope** (DBREF) | | 현재 범위 목록을 비우고 전달된 DBREF를 현재 범위로 만든다. |
| **AddScope** (DBREF) | | 전달된 DBREF를 현재 범위 목록에 추가한다. |
| **Scope** (DBREF ARRAY) | | 현재 범위 목록을 전달된 DBREF 목록으로 교체한다. |
| **AppendScope** (DBREF ARRAY) | | 전달된 DBREF 목록을 범위 목록에 추가(append)한다. |
| **ClearScope**() | | 현재 범위 목록을 비운다. |
| **Filter** (EXPRESSION) | | 컬렉션에 적용할 필터를 설정한다. |
| **ClearFilter** () | | 컬렉션에 적용된 필터를 비운다. |
| **Type** (STRING) | | 현재 범위 타입 목록을 비우고 전달된 요소(element) 타입을 추가한다. |
| **AddType**(STRING) | | 전달된 요소 타입을 범위 타입 목록에 추가한다. |
| **ClearTypes**() | | 컬렉션에 적용될 타입들을 비운다. |
| **Types** (ARRAY elements) | | 범위 요소 타입 목록을 전달된 목록(elements)으로 교체한다. |
| **AppendTypes** (ARRAY types) | | 전달된 목록(types)을 범위 타입 목록에 추가(append)한다. |
| **Initialise**() | | 쿼리 작업이 컬렉션 규칙을 다시 평가하도록 평가 목록(evaluate list)을 초기화한다. 인덱스 위치를 1로 설정한다. |
| **Filter**() | EXPRESSION | 데이터베이스 요소를 필터링하는 데 사용된 표현식을 반환한다. |
| **Scope**() | DBREF ARRAY | 스캔할 데이터베이스 요소 목록을 반환한다. |
| **Types**() | STRING ARRAY | 수집될 데이터베이스 요소 타입의 목록을 반환한다. |
| **Results**() | DBREF ARRAY | 전체 컬렉션을 반환한다. |
| **Next**(REAL n) | DBREF ARRAY | 현재 인덱스 위치에서 시작하여 n개의 요소로 구성된 컬렉션의 하위 배열(sub array)을 반환한다. |
| **Index**() | [[REAL\|REAL Object]] | Next()에서 사용 중인 카운트의 현재 인덱스를 반환한다. |
| **Size** () | [[REAL\|REAL Object]] | 컬렉션에 있는 요소의 수를 반환한다. |

## 노트 (Notes)
- 사용자는 범위를 설정하지 않거나 ClearScope() 메소드를 사용하여 컬렉션 객체의 범위를 전체 MDB로 설정할 수 있다.