---
tags: [PML2, E3D, PDMS, Database]
aliases: [DB Object]
classification: PDMS Objects
---

# [[DB]]

## 개요
이 객체의 메소드들은 Database element에서 Object로의 접근을 용이하게 하여 Appware의 성능 향상을 돕는다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Name** | [[STRING\|STRING Object]] | 데이터베이스의 이름 (최대 32자). |
| **Description** | [[STRING\|STRING Object]] | 데이터베이스 설명 (최대 120자). |
| **Access** | [[STRING\|STRING Object]] | 액세스 유형 (UPDATE, MULTIWRITE, CONTROLLED). |
| **Claim** | [[STRING\|STRING Object]] | 다중 쓰기(multi-write) 데이터베이스에 대한 Claim 모드 (EXPLICIT, IMPLICIT). |
| **File** | [[STRING\|STRING Object]] | 데이터베이스 파일 이름 (최대 17자). |
| **Foreign** | [[STRING\|STRING Object]] | FOREIGN 또는 LOCAL. |
| **Number** | [[STRING\|STRING Object]] | 데이터베이스 번호. |
| **Team** | TEAM | 소유 팀 (Owning Team). |
| **Type** | [[STRING\|STRING Object]] | 데이터베이스 유형 (예: DESI). |
| **Refno** | [[STRING\|STRING Object]] | 데이터베이스 참조 번호를 포함하는 문자열. |
| **Primary** | [[STRING\|STRING Object]] | 글로벌 프로젝트의 현재 위치에서 데이터베이스가 PRIMARY인지 SECONDARY인지를 식별한다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **MDBList** () | [[ARRAY\|ARRAY Object]] | 이 DB를 포함하는 MDB 목록. |
| **Size** () | [[REAL\|REAL Object]] | 페이지 단위의 파일 크기. |
| **Sessions** () | ARRAY OF DBSESS | 현재 데이터베이스의 모든 세션. |
| **Lastsession** () | DBSESS | 데이터베이스의 마지막 세션 정보. |
| **DB** (DBREF) | DB | DBREF가 주어졌을 때 DB 객체를 반환한다. |
| **DB** (STRING) | DB | 이름이나 참조 번호가 주어졌을 때 DB 객체를 반환한다. |

## 커맨드 (Commands)

```
!ARRAY = DBS $ 현재 프로젝트의 DB 배열을 반환한다
```

## 노트 (Notes)
- 이 메소드들은 다음과 같은 방식으로 사용될 수 있다 (모든 경우 !!CE는 DB DATABASE 요소로 가정되며, !!CE.Name은 요소의 이름을 포함하는 STRING 객체로 가정된다).
- 이 메소드들은 Database element에서 Object로 쉽게 이동할 수 있게 하여 Appware의 성능 향상을 돕는다.