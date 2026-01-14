---
tags: [PML2, E3D, Geometry, Grid]
aliases: [LINEARGRID Object]
classification: 3D Geometry Objects
---

# [[LINEARGRID]]

## 개요
LINEARGRID 객체는 선형 그리드(Linear Grid)를 정의하고 생성하는 데 사용된다. 이 객체는 위치, 방향, 그리고 X 및 Y 방향의 간격 정보를 포함하는 구조 보조 도구이다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Position** | [[position\|position Object]] | 그리드의 원점 |
| **Orientation** | [[orientation\|orientation Object]] | 그리드의 방향 |
| **XSpacing** | [[REAL\|REAL Object]] | X 방향의 간격 |
| **YSpacing** | [[REAL\|REAL Object]] | Y 방향의 간격 |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Lineargrid** ( POSITION, ORIENTATION, REAL, REAL) | LINEARGRID | 주어진 POSITION, ORIENTATION, 그리고 X 및 Y 간격으로 그리드를 생성한다. |
| **String** () | [[STRING\|STRING Object]] | 그리드를 문자열로 반환한다. |
| **GridPoint** (REAL, REAL) | [[position\|position Object]] | 그리드 원점으로부터 전달된 X 및 Y 선의 교차점 위치를 반환한다. 값은 원점의 측면에 따라 양수 또는 음수가 될 수 있다. |
| **Snap** (POSITION) | [[position\|position Object]] | 그리드 평면에 매핑될 때, 전달된 위치에서 가장 가까운 교차점을 반환한다. |
| **Snap** (LINE) | [[position\|position Object]] | 전달된 선과 그리드 평면의 교차점에서 가장 가까운 교차점을 반환한다. |
| **Snap** (POINTVECTOR) | [[position\|position Object]] | 전달된 포인트 벡터(point vector)와 그리드 평면의 교차점에서 가장 가까운 교차점을 반환한다. |
| **SnaptoCentre** (POSITION) | [[position\|position Object]] | 그리드 평면에 매핑될 때, 전달된 위치에서 가장 가까운 메쉬 셀 중심점을 반환한다. |
| **SnaptoCentre** (LINE) | [[position\|position Object]] | 전달된 선과 그리드 평면의 교차점에서 가장 가까운 메쉬 셀 중심점을 반환한다. |
| **SnaptoCentre** (POINTVECTOR) | [[position\|position Object]] | 전달된 포인트 벡터와 그리드 평면의 교차점에서 가장 가까운 메쉬 셀 중심점을 반환한다. |
| **Plane** () | PLANE | 그리드를 평면(plane) 객체로 반환한다. |
| **XYOffset** (POSITION) | XYPOSITION | 그리드 평면 원점으로부터의 XY 오프셋 관점에서, 그리드 평면에 매핑된 위치를 반환한다. |