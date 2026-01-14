---
tags: [PML2, E3D, Database, Reference]
aliases: [DBREF Object]
classification: PDMS Objects
---

# [[DBREF]]

## 개요
주어진 문자열로 설정된 값을 가진 DBREF 객체를 생성한다. DBREF는 그것이 가리키는 데이터베이스 요소(DB elements)의 속성을 가진 것처럼 동작한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Dbref** (STRING) | [[dbref\|dbref Object]] | 주어진 STRING으로 값을 설정하여 DBREF 객체를 생성한다. |
| **Dbref** (STRING, FORMAT) | [[dbref\|dbref Object]] | 위와 동일하다. FORMAT 인수는 Forms 및 Menus와의 일관성을 위해 필요하다. |
| **Attribute** (STRING Name) | ANY | 지정된 이름의 속성(Attribute) 값을 반환한다. |
| **Attributes** () | ARRAY OF STRING | DBREF는 가리키고 있는 DB 요소의 속성을 가진 것처럼 보인다. |
| **BadRef** () | [[BOOLEAN\|BOOLEAN Object]] | DBREF가 유효하지 않은 경우(탐색할 수 없는 경우) TRUE를 반환한다. |
| **Delete** () | NO RESULT | PML DBREF를 삭제한다 (가리키고 있는 데이터베이스 요소가 아님). |
| **MCount** () | [[REAL\|REAL Object]] | 참조된 요소의 멤버 수를 반환한다. |
| **MCount** (STRING type) | [[REAL\|REAL Object]] | 지정된 타입의 참조된 요소 멤버 수를 반환한다. |
| **String** (FORMAT) | [[STRING\|STRING Object]] | 글로벌 FORMAT 객체의 설정을 사용하여 STRING으로 변환한다. |
| **Line** ([CUT/UNCUT]) | LINE | SCTN/GENSEC 요소의 cut/uncut pline을 경계가 있는 선(bounded line)으로 반환한다. |
| **PPosition** (REAL) | [[position\|position Object]] | 데이터베이스 요소의 지정된 Ppoint 위치를 반환한다. |
| **PDirection** (REAL) | [[Direction\|Direction Object]] | 데이터베이스 요소의 지정된 Ppoint 방향을 반환한다. |