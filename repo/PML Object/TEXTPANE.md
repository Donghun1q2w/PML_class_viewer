---
tags: [PML2, E3D, Grid, Construction, Geometry]
aliases: [PLANTGRID Object]
classification: 3D Geometry Objects
---

# [[PLANTGRID]]

## 개요
PLANTGRID 객체는 그리드 구축 보조 도구(Construction Aids)이다. 이 객체는 위치, 방향, 그리고 X 및 Y 방향의 간격 배열을 사용하여 그리드를 정의한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Position** | [[position\|position Object]] | 그리드의 원점. |
| **Orientation** | [[orientation\|orientation Object]] | 그리드의 방향. |
| **XSpacings** | REAL ARRAY | X 방향의 간격 배열이며, 각 간격은 이전 간격에 상대적이다. |
| **YSpacings** | REAL ARRAY | Y 방향의 간격 배열이며, 각 간격은 이전 간격에 상대적이다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Plantgrid** (POSITION, ORIENTATION, ARRAY, ARRAY) | PLANTGRID | 주어진 POSITION과 ORIENTATION, 그리고 배열에 지정된 X 및 Y 간격으로 그리드를 생성한다. |
| **Xsize** () | [[REAL\|REAL Object]] | X 방향의 최대 크기를 반환한다. |
| **Ysize** () | [[REAL\|REAL Object]] | Y 방향의 최대 크기를 반환한다. |
| **OutofBounds** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 포인트가 그리드 경계 내에 위치하는지 여부를 반환한다. |