---
tags: [PML2, E3D, IDList, IDLIST, Drawlist, Database]
aliases: [IDList Object]
classification: PML Object
---

# [[IDList]]

## 개요
IDList Object는 IDLIST 데이터베이스 엘리먼트의 요소에 접근하고 조작하는 기능을 제공한다. IDList Object의 요소는 유효한 design drawlist 엘리먼트를 소유하거나 drawlist 엘리먼트에 의해 소유된 significant element여야 한다. Design drawlist 엘리먼트 하위 레벨의 엘리먼트는 이 Object를 통해 조작할 수 없다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **idlist** (DBREF) | IDList | 주어진 IDLIST의 DBREF로부터 PML IDList Object를 생성한다. significant element가 발견될 때까지 소유권 계층 구조를 검색하고, 이를 Idlist에 추가한다. |
| **add** (DBREF) | No Result | IDLIST에 ADDE를 추가한다. 동일한 엘리먼트 또는 그 조상에 대한 ADDE가 이미 존재하고(중간에 REME 없이), 해당 항목이 'active' 상태라면 아무 작업도 수행하지 않는다. 중간에 동일한 REME가 있으면 해당 REME를 제거한다. |
| **add** (SELECTION) | No Result | 선택 세트(Selection set) 전체에 대한 ADDE를 개별 DBREF와 동일한 방식으로 IDList에 추가한다. |
| **remove** (DBREF) | No Result | 목록에 이 엘리먼트에 대한 ADDE가 존재하면 제거한다. 만약 이 엘리먼트의 조상에 대한 ADDE가 존재하면 REME를 삽입한다. |
| **remove** (SELECTION) | No Result | 단일 엘리먼트를 제거할 때와 동일한 규칙을 사용하여 선택 세트에 정의된 모든 ADDE를 제거한다. |
| **copy** (IDLIST other) | [[BOOLEAN\|BOOLEAN Object]] | idlist를 비우고, 다른 idlist(other)의 모든 항목을 추가한다. 복사가 성공하면 TRUE를 반환한다. |
| **clear** () | No Result | idlist에서 모든 엘리먼트를 제거한다. |
| **query** () | ARRAY of STRINGS | idlist의 모든 엘리먼트를 항목화하여 문자열 배열을 반환한다 (형식: `ADDE element` 또는 `REME element`). |

## 노트 (Notes)
- ADDE를 추가하기 전에, Object는 목록에 'active' ADDE(동일한 오브젝트에 대한 중간 REME가 없는 동일한 엘리먼트에 대한 ADDE)가 있는지 확인한다. 만약 있다면 다시 추가하지 않으며, REME의 경우도 마찬가지이다.
- ADDE 또는 REME를 제거할 때, 시스템은 목록의 맨 아래에서 시작하여 역순으로 작업하며 요청된 항목을 제거한다.