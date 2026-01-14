---
tags: [PML2, E3D, Geometry, 3D]
aliases: [PLANE Object]
classification: 3D Geometry Objects
---

# [[PLANE]]

## 개요
PLANE Object는 3D 기하학 객체(3D Geometry Object)로 분류된다. 이 객체는 평면의 원점(Position)과 방향(Orientation)을 정의하는 멤버를 포함한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Orientation** | [[orientation\|orientation Object]] | 평면의 오리엔테이션 (방향). |
| **Position** | [[position\|position Object]] | 평면의 원점. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Plane** (POSITION, ORIENTATION) | PLANE | 주어진 POSITION(위치)과 ORIENTATION(방향)으로 PLANE을 생성한다. |
| **String** () | [[STRING\|STRING Object]] | 평면을 문자열로 반환한다. |
| **Direction** (DIRECTION) | [[Direction\|Direction Object]] | 오리엔테이션의 Z 구성 요소는 X 및 Y 구성 요소를 유지하는 표준 PDMS 방식을 사용한다. |
| **Towards** (POSITION) | NO RESULT | 평면의 방향(오리엔테이션의 Z 성분) 멤버를 수정하여 해당 위치를 향하도록 한다. |
| **Intersection** (LINE) | [[position\|position Object]] | 전달된 무한 직선과 평면 정의의 교차점을 반환한다. |
| **Intersection** (POINT VECTOR) | [[position\|position Object]] | 전달된 포인트 벡터와 평면 정의의 교차점을 반환한다. |
| **Intersections** (ARC) | ARRAY OF POSITIONS | 전달된 호(arc)와 평면 정의의 교차점을 반환한다. |
| **Intersection** (PLANE, PLANE) | [[position\|position Object]] | 세 평면의 교차 위치를 반환한다. |
| **PointVector** () | POINT VECTOR | 평면의 법선(normal)과 동일한 방향을 가진 평면 원점에서의 포인트 벡터를 반환한다. |
| **ThreeDPosition** (XYPOSITION) | [[position\|position Object]] | 평면 원점으로부터 오프셋된 XYPOSITION의 3D 위치를 반환한다. |
| **Near** (POSITION) | [[position\|position Object]] | 전달된 위치에 대해 평면 정의 상의 가장 가까운 위치를 반환한다. |
| **Line** (REAL) | LINE | 평면 법선 방향으로 주어진 길이의 선을 반환한다. |
| **Intersection** (PLANE) | LINE | 전달된 평면과 평면 정의의 교차선을 반환한다. 선의 시작 위치는 전달된 평면에 투영된 평면 정의의 원점이다. 선의 방향은 시작점에서 참조 평면에 투영된 전달된 평면의 위치까지이다. 시작점과 끝점이 일치하는 경우, 위에서 설명한 대로 정의된 시작 위치를 가진 길이 1000mm의 선이 반환된다. |
| **XYOffset** (Position) | XYPOSITION | 평면 원점으로부터의 XY 오프셋 관점에서 평면에 매핑된 위치를 반환한다. |