---
tags: [PML2, E3D, PDMS, Database, Inter-DB]
aliases: [MACRO Object]
classification: PDMS Objects
---

# [[MACRO]]

## 개요
MACRO Object는 PDMS Object 분류에 속하며, Inter-DB 매크로와 관련된 정보를 다루는 객체이다. 이 객체는 매크로 파일 이름, 소스 및 대상 데이터베이스, 매크로 번호 등의 속성을 포함한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Filename** | [[STRING\|STRING Object]] | Inter-DB 매크로 파일 이름 (최대 17자). |
| **From** | DB | Inter-DB 연결 매크로의 소스 DB. |
| **Number** | [[REAL\|REAL Object]] | Inter-DB 매크로 번호. |
| **To** | DB | Inter-DB 연결 매크로의 대상 DB. |

## 커맨드 (Commands)
```pml
!ARRAY = MACROS $ Returns an array of all the MACRO objects in the project
```