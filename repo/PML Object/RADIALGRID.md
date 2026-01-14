---
tags: [PML2, E3D, 3D Geometry Objects]
aliases: [RADIALGRID Object]
classification: 3D Geometry Objects
---

# [[RADIALGRID]]

## 개요
RADIALGRID 객체는 3D 기하학 객체 중 하나입니다. 주어진 위치(Position)와 방향(Orientation), 그리고 배열로 지정된 각도와 반경을 사용하여 그리드를 생성합니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Position** | [[position\|position Object]] | 그리드의 원점. |
| **Orientation** | [[orientation\|orientation Object]] | 그리드의 방향. |
| **Radii** | REAL ARRAY | 그리드의 반경들. |
| **Angles** | REAL ARRAY | X축(0도)으로부터의 각도 간격. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Radialgrid** ( POSITION, ORIENTATION, ARRAY, ARRAY) | RADIALGRID | 주어진 위치와 방향, 그리고 배열에 지정된 각도와 반경으로 그리드를 생성합니다. |