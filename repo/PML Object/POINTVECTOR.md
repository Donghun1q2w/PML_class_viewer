---
tags: [PML2, E3D, 3D Geometry Objects, PointVector]
aliases: [POINTVECTOR Object]
classification: 3D Geometry Objects
---

# [[POINTVECTOR]]

## 개요
POINTVECTOR Object는 3D 공간 상의 위치(Position)와 방향(Direction)을 정의하는 객체이다. 이 객체는 특정 원점과 방향 벡터를 기반으로 기하학적 연산을 수행하는 데 사용된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Direction** | [[Direction\|Direction Object]] | 점(point)의 방향 |
| **Position** | [[position\|position Object]] | 점(point)의 원점 |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Pointvector** (POSITION, DIRECTION) | POINTVECTOR | 주어진 POSITION과 DIRECTION으로 POINTVECTOR를 생성한다. |
| **String** () | [[STRING\|STRING Object]] | POINTVECTOR를 문자열(STRING)로 반환한다. |
| **Offset** (REAL) | POINTVECTOR | 전달된 거리(distance)만큼 해당 방향으로 오프셋(offset)된 포인트 벡터를 반환한다. |
| **Towards** (POSITION) | POINTVECTOR | 원래의 위치(position)를 유지하면서, 해당 위치에서 전달된 위치(position)를 향하는 방향(direction)으로 구성된 포인트 벡터를 반환한다. |
| **Through** (POSITION) | POINTVECTOR | 포인트 라인(point line)과, 전달된 위치(position)를 통과하며 포인트 라인에 수직인 평면과의 교차점에 있는 포인트 벡터를 반환한다. |
| **Intersection** (POINTVECTOR) | [[position\|position Object]] | 두 포인트 벡터의 교차 위치(position)를 반환한다. |
| **Intersection** (LINE) | [[position\|position Object]] | 포인트 벡터와 제공된 라인(line)과의 교차 위치를 반환한다. |
| **Intersection** (PLANE) | [[position\|position Object]] | 포인트 벡터와 제공된 평면(plane)과의 교차 위치를 반환한다. |
| **Intersections** (ARC) | ARRAY OF POSITIONS | 포인트 벡터와 제공된 아크(arc)와의 교차 위치들을 반환한다. |
| **Plane** () | PLANE | 포인트 벡터의 위치와 동일한 원점(origin)과 포인트 벡터의 방향과 동일한 법선 방향(normal direction)을 가진 평면(plane)을 반환한다. |
| **Line** (REAL) | LINE | 포인트 벡터의 위치와 동일한 시작 위치, 포인트 벡터의 방향과 동일한 방향, 그리고 제공된 길이(length)와 동일한 길이를 가진 라인(line)을 반환한다. |