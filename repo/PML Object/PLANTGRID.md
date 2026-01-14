---
tags: [PML2, E3D, Geometry, Grid]
aliases: [PLANTGRID Object]
classification: 3D Geometry Objects
---

# [[PLANTGRID]]

## 개요
주어진 POSITION, ORIENTATION, 그리고 배열에 지정된 X, Y 간격을 사용하여 그리드를 생성하는 객체이다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Position** | [[position\|position Object]] | 그리드의 원점. |
| **Orientation** | [[orientation\|orientation Object]] | 그리드의 방향. |
| **XSpacings** | REAL ARRAY | X 방향의 간격 배열, 각 간격은 이전 간격에 상대적임. |
| **YSpacings** | REAL ARRAY | Y 방향의 간격 배열, 각 간격은 이전 간격에 상대적임. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Plantgrid** (POSITION, ORIENTATION, ARRAY, ARRAY) | PLANTGRID | 주어진 POSITION, ORIENTATION, 그리고 배열에 지정된 X, Y 간격으로 그리드를 생성한다. |
| **Xsize** () | [[REAL\|REAL Object]] | X 방향의 최대 크기. |
| **Ysize** () | [[REAL\|REAL Object]] | Y 방향의 최대 크기. |
| **OutofBounds** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 점이 그리드 경계 내에 있는지 여부를 반환한다. |