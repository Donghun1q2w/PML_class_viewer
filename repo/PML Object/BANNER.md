---
tags: [PML2, E3D, PDMS, Banner, System]
aliases: [BANNER Object]
classification: PDMS Objects
---

# [[BANNER]]

## 개요
BANNER Object는 회사 이름, 저작권, 라이브러리 정보, 메인 윈도우 제목 및 PDMS 릴리스 상태와 같은 정보를 제공하는 객체이다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Company** | [[STRING\|STRING Object]] | 회사 이름 (최대 120자). |
| **Copyright** | [[STRING\|STRING Object]] | AVEVA 저작권 (최대 80자). |
| **Libraries** | ARRAY OF STRINGS | 라이브러리 이름. |
| **Name** | [[STRING\|STRING Object]] | 메인 윈도우의 제목 (최대 13자). |
| **Short** | [[STRING\|STRING Object]] | 회사 이름의 줄임말. |
| **Status** | [[STRING\|STRING Object]] | PDMS 릴리스 상태. |

## 커맨드 (Commands)
```pml
!BANNVAR = BANNER! $ BANNER 객체를 반환한다
```