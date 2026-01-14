---
tags: [PML2, E3D, PDMS, Database]
aliases: [MDB Object]
classification: PDMS Objects
---

# [[MDB]]

## 개요
MDB Object는 PDMS Objects 분류에 속하는 객체 유형이다. 프로젝트 내의 Multiple Database(MDB)를 나타낸다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Name** | [[STRING\|STRING Object]] | MDB의 이름 (최대 32자). |
| **Description** | [[STRING\|STRING Object]] | MDB 설명 (최대 120자). |
| **Refno** | [[STRING\|STRING Object]] | 데이터베이스 참조 번호를 포함하는 문자열. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **MDB** (DBREF) | MDB | DBREF가 주어졌을 때 MDB 객체를 반환한다. |
| **MDB** (STRING) | MDB | 이름이나 참조 번호가 주어졌을 때 MDB 객체를 반환한다. |
| **Current** () | ARRAY OF DBS | 현재 데이터베이스들을 DB 객체의 배열로 반환한다. |
| **Deferred** () | ARRAY OF DBS | 지연된(Deferred) 데이터베이스들을 DB 객체의 배열로 반환한다. |
| **Mode** () | ARRAY OF STRINGS | MDB의 각 현재 DB에 대해 'NR' 또는 'RW'를 반환한다. |

## 커맨드 (Commands)
```pml
!D = OBJECT MDB(!!CE)
!D = OBJECT MDB(!!CE.Name)
!D = !!CE.MDB()
!D = !!CE.Name.MDB()

!ARRAY= MDBS      $ Returns an array of MDB objects in the project
```

## 노트 (Notes)
- 이 메소드들 중 어느 것도 원본 객체를 수정하지 않는다.
- 모든 경우에, !!CE는 DB 데이터베이스 요소로 가정되며 !!CE.Name은 해당 요소의 이름을 포함하는 STRING 객체로 가정된다.
- 이러한 메소드들은 Database 요소에서 Object로의 변환을 쉽게 만들어 AppWare의 성능 향상을 돕는다.