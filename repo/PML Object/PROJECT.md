---
tags: [PML2, E3D, PDMS, Project_Management, Database_Administration]
aliases: [PROJECT Object]
classification: PDMS Objects
---

# [[PROJECT]]

## 개요
PROJECT Object는 PDMS/E3D 프로젝트의 속성 및 관련 정보에 접근하는 데 사용된다. 프로젝트의 이름, 설명, 활성 사용자 수, 위치(Location), 세션(Session), 데이터베이스(DB) 목록 등의 정보를 조회하거나 설정할 수 있다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Name** | [[STRING\|STRING Object]] | 프로젝트 이름 (최대 120자). |
| **Evar** | [[STRING\|STRING Object]] | 프로젝트 환경 변수 (예: SAM000). |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Active**() | [[REAL\|REAL Object]] | 프로젝트의 활성 사용자 수. |
| **Code**() | [[STRING\|STRING Object]] | 3글자 프로젝트 코드 (예: SAM). |
| **Description**() | [[STRING\|STRING Object]] | 프로젝트 설명 (최대 120자). |
| **Mbcharset**() | [[STRING\|STRING Object]] | 멀티바이트 문자 세트 번호. |
| **Message**() | [[STRING\|STRING Object]] | 프로젝트 메시지 (프로젝트에 대한 정보, 최대 120자). |
| **Name**() | [[STRING\|STRING Object]] | 프로젝트 이름. |
| **Number**() | [[STRING\|STRING Object]] | 프로젝트 번호 (최대 17자). |
| **Isglobal**() | [[BOOLEAN\|BOOLEAN Object]] | 글로벌 프로젝트 여부. |
| **Locations**() | ARRAY OF LOCATION | 프로젝트의 모든 위치(Location) 배열 반환. |
| **CurrentLocation**() | LOCATION | 실제 현재 위치(Location) 반환. |
| **Sessions**() | ARRAY OF SESSIONS | (현재 위치에서의) 모든 세션 배열 반환. |
| **CurrentSession**() | SESSION | (현재 위치에서의) 현재 세션 반환. |
| **Dblist**() | ARRAY OF DB OBJECTS | 프로젝트 내 데이터베이스 목록. |
| **MDBList**() | ARRAY OF MDBS | 현재 위치의 프로젝트 내 모든 MDB 배열 반환. |
| **UserList**() | ARRAY OF USERS | 현재 위치의 프로젝트 내 모든 USER 배열 반환. |
| **Macros**() | ARRAY OF MACROS | 현재 위치의 프로젝트 내 MISC db에 있는 모든 Inter-db 매크로 배열 반환. |
| **Messages**() | ARRAY OF STRINGS | 현재 위치의 프로젝트 내 MISC db에 있는 모든 메시지 배열 반환. |

## 커맨드 (Commands)

```pml
!ARRAY = PROJECTS
$ 프로젝트 환경 변수가 설정된 모든 PROJECT 객체의 배열을 반환한다.

!PROJECTVAR = CURRENT PROJECT
$ 현재 프로젝트 객체를 반환한다.
```