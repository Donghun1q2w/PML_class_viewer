---
tags: [PML2, E3D, LOCATION, Project, Database]
aliases: [LOCATION Object]
classification: 3D Geometry Objects
---

# [[LOCATION]]

## 개요
LOCATION Object는 프로젝트 내의 위치(Location) 정보를 다루는 객체이다. Location의 이름, 설명, 식별자(Locid), 데이터베이스 참조 번호(Refno) 등의 속성을 포함하며, 현재 위치 여부를 확인할 수 있다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Name** | [[STRING\|STRING Object]] | Location 이름. |
| **Description** | [[STRING\|STRING Object]] | 설명 (최대 120자). |
| **Locid** | [[STRING\|STRING Object]] | Location 식별자. |
| **Refno** | [[STRING\|STRING Object]] | 데이터베이스 참조 번호를 포함하는 문자열. |
| **IsCurrent** | [[BOOLEAN\|BOOLEAN Object]] | 현재 위치(Location)인 경우 True. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **LOCATION** (DBREF) | LOCATION | DBREF가 주어졌을 때 LOCATION 객체를 반환한다. |
| **LOCATION** (STRING) | LOCATION | 이름이나 참조 번호가 주어졌을 때 LOCATION 객체를 반환한다 (Global projects 전용). |
| **Dblist** () | ARRAY OF DB | 할당된 DB들에 대한 DB 객체 배열을 반환한다. 이 메소드는 원본 객체를 수정하지 않는다. |
| **Sessions** () | ARRAY OF SESSIONS | 해당 Location의 COMMs db에서 추출된 모든 세션의 배열을 반환한다. 이 메소드는 원본 객체를 수정하지 않는다. |
| **String** () | [[STRING\|STRING Object]] | Location 이름을 포함하는 문자열을 반환한다. 이 메소드는 원본 객체를 수정하지 않는다. |

## 노트 (Notes)
- `Sessions()` 메소드는 원격 삭제(remote expunging)에 필요한 정보를 제공한다. 이 메소드는 현재 위치가 아닌 다른 위치에 대해 데몬(daemon) 활동을 유발한다.