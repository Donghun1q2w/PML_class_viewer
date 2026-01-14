---
tags: [PML2, E3D, IDList, Database, Drawlist]
aliases: [IDList Object]
classification: PDMS Objects
---

# [[IDList]]

## 개요
IDList 객체는 IDLIST 데이터베이스 요소의 항목에 접근하고 조작하기 위한 기능을 제공한다. IDList 객체의 요소는 유효한 설계 도면 목록(design drawlist) 요소를 소유하거나 도면 목록 요소에 의해 소유되는 유의미한(significant) 요소여야 한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **idlist** (DBREF) | IDLIST | 지정된 IDLIST의 DBREF로부터 PML IDList 객체를 생성한다. 유의미한 요소를 찾을 때까지 소유권 계층 구조를 위로 검색하고, 이를 Idlist에 추가한다. |
| **add** (DBREF) | NO RESULT | IDLIST에 ADDE를 추가한다. 동일한 요소 또는 (개입하는 REME 없이) 그 조상 중 하나에 대한 ADDE가 이미 존재하는 경우 아무 작업도 수행하지 않는다. 개입하는 동일한 REME가 있는 경우, 그 REME는 제거된다. |
| **add** (SELECTION) | NO RESULT | 개별 DBREF와 동일한 방식으로 전체 선택 세트(selection set)에 대한 ADDE들을 IDList에 추가한다. |
| **remove** (DBREF) | NO RESULT | 목록에 해당 요소에 대한 ADDE가 존재하면 제거된다. 해당 요소의 조상에 대한 ADDE가 존재하면 REME가 삽입된다. |
| **remove** (SELECTION) | NO RESULT | 단일 요소를 제거할 때와 동일한 규칙을 사용하여 선택 세트에 정의된 모든 ADDE를 제거한다. |
| **copy** (IDLIST other) | [[BOOLEAN\|BOOLEAN Object]] | idlist를 비우고 다른(other) idlist의 모든 항목을 추가한다. 복사가 성공하면 TRUE를 반환한다. |
| **clear** ( ) | NO RESULT | idlist에서 모든 요소를 제거한다. |
| **query** ( ) | ARRAY of STRINGS | idlist의 모든 요소를 항목화하여 'ADDE element' 또는 'REME element' 형식의 문자열 배열을 반환한다. |