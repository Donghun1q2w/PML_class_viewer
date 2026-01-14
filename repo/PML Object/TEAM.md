---
tags: [PML2, E3D, PDMS, Administration, Database]
aliases: [TEAM Object]
classification: PDMS Objects
---

# [[TEAM]]

## 개요
TEAM 오브젝트는 프로젝트 내의 TEAM 요소에 대한 인터페이스를 제공한다. 이 오브젝트는 TEAM의 이름, 설명, 참조 번호 등의 속성을 조회하거나, 해당 TEAM이 소유한 데이터베이스(DB) 및 소속된 사용자(USER)의 목록을 반환하는 데 사용된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Name** | [[STRING\|STRING Object]] | TEAM의 이름, 최대 32자. |
| **Description** | [[STRING\|STRING Object]] | TEAM 설명, 최대 120자. |
| **Refno** | [[STRING\|STRING Object]] | 데이터베이스 참조 번호를 포함하는 문자열. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **TEAM** (DBREF) | TEAM | DBREF가 주어졌을 때 TEAM 오브젝트를 반환한다. |
| **TEAM** (STRING) | TEAM | 이름 또는 참조 번호가 주어졌을 때 TEAM 오브젝트를 반환한다. |
| **DbList** () | ARRAY OF DB | TEAM이 소유한 DB들의 목록. |
| **UserList** () | ARRAY OF USER | TEAM에 속한 USER들의 목록. |

## 커맨드 (Commands)

```pml
!ARRAY = TEAMS   $ Returns an array of TEAMs
```