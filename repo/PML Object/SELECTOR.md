---
tags: [PML2, E3D, Geometry, LINE]
aliases: [LINE Object]
classification: 3D Geometry Objects
---

# [[LINE Object]]

## 개요
LINE Object는 POINTVECTOR Object와 밀접한 관련이 있는 3D 기하학 객체이다. 시작 위치(StartPosition)와 끝 위치(EndPosition)를 통해 선을 정의한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **StartPosition** | [[position\|position Object]] | 라인의 시작 위치. |
| **EndPosition** | [[position\|position Object]] | 라인의 끝 위치. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Line**(POSITION first, POSITION second) | LINE | 주어진 첫 번째(first)와 두 번째(second) 위치 사이에 LINE을 생성한다. (생성자) |
| **String**() | [[STRING\|STRING Object]] | 라인을 STRING으로 반환한다. |
| **Direction**() | [[Direction\|Direction Object]] | 라인의 방향을 나타내는 DIRECTION을 반환한다. |
| **Direction**(DIRECTION way) | LINE | 동일한 시작 위치와 길이를 가지지만, 주어진 방향(way)을 따르는 새로운 라인을 생성한다. |
| **On**(POSITION where) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 위치(where)가 무한한 선상에 놓여 있다면 TRUE를 반환한다. |
| **On**(POSITION where, BOOLEAN bounded) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 위치(where)가 선상에 놓여 있다면 TRUE를 반환한다. bounded가 지정되면 해당 점이 유한한 선분 위에 있는지도 확인한다. |
| **OnProjected**(POSITION where) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 위치(where)가 라인에 투영되었을 때 유한한 선분 내에 놓인다면 TRUE를 반환한다. |
| **Intersection**(LINE other) | [[position\|position Object]] | 정의된 라인 상에서 전달된 LINE(other)과의 교차점을 반환한다. |
| **Intersection**(POINT point, VECTOR vector) | [[position\|position Object]] | 정의된 라인 상에서 전달된 POINTVECTOR(point, vector)와의 교차점을 반환한다. |
| **Intersection**(PLANE plane) | LINE | 정의된 라인 상에서 평면(plane)과의 교차 라인을 반환한다. |
| **Intersections**(ARC arc) | ARRAY OF POSITIONS | 정의된 라인 상에서 호(arc)와의 교차점들을 반환한다. |
| **Near**(POSITION position) | [[position\|position Object]] | 주어진 위치(position)에서 라인 정의 상 가장 가까운 위치를 반환한다. |
| **Proportion**(REAL proportion) | [[position\|position Object]] | StartPosition으로부터 "유한한" 라인을 따라 비율(proportion)에 해당하는 위치를 반환한다.\u003cbr\u003e(1보다 큰 값은 라인 끝을 벗어난 위치, 0보다 작은 값은 라인 시작 전의 위치를 반환함) |
| **Length**() | [[REAL\|REAL Object]] | 라인의 길이를 반환한다. |
| **Distance**(LINE other) | [[REAL\|REAL Object]] | 라인 정의와 다른 라인(other) 사이의 최소 거리를 반환한다. |
| **Distance**(POSITION position) | [[REAL\|REAL Object]] | 라인 정의와 위치(position) 사이의 최소 거리를 반환한다. |
| **Plane**() | PLANE | 라인 객체의 StartPosition과 Direction을 사용하여 평면(plane) 객체를 반환한다. |
| **Pointvector**() | POINTVECTOR | 라인 객체의 StartPosition과 Direction을 사용하여 POINTVECTOR 객체를 반환한다. |
| **SetLengthStart**(REAL length) | LINE | 원래의 StartPosition과 방향을 유지하면서, 길이(length)에 맞춰 EndPosition이 조정된 새로운 라인을 반환한다. |
| **SetLengthEnd**(REAL length) | LINE | 원래의 EndPosition과 방향을 유지하면서, 길이(length)에 맞춰 StartPosition이 조정된 새로운 라인을 반환한다. |
| **Towards**(POSITION position) | LINE | 원래 라인과 동일한 StartPosition과 상대적인 EndPosition(길이)을 가지지만, 방향이 시작 위치에서 주어진 위치(position)를 향하는 새로운 라인 객체를 반환한다. |
| **From**(POSITION position) | LINE | 원래의 EndPosition을 유지하면서, StartPosition이 주어진 위치(position)로 설정된 라인을 반환한다. |
| **To**(POSITION position) | LINE | 원래의 StartPosition을 유지하면서, EndPosition이 주어진 위치(position)로 설정된 라인을 반환한다. |
| **ExtendStart**(REAL distance) | LINE | StartPosition이 라인의 반대 방향으로 거리(distance)만큼 확장된 새로운 LINE을 반환한다. |
| **ExtendEnd**(REAL distance) | LINE | EndPosition이 라인의 방향으로 거리(distance)만큼 확장된 새로운 LINE을 반환한다. |
| **ExtendStart**(PLANE plane) | LINE | StartPosition이 평면(plane)까지 확장된 새로운 LINE을 반환한다. |
| **ExtendEnd**(PLANE plane) | LINE | EndPosition이 평면(plane)까지 확장된 새로운 LINE을 반환한다. |
| **ReverseSense**() | LINE | StartPosition과 EndPosition이 서로 바뀐 라인을 반환한다. |
| **Projected**(PLANE plane) | LINE | 평면(plane)에 정규화된 LINE 정의를 반환한다. |
| **Parallel**(POSITION position) | LINE | 라인 객체의 정의와 평행하며 주어진 위치(position)를 통과하는 라인을 반환한다. 다른 모든 멤버는 복사된다. |
| **Offset**(DIRECTION direction, REAL offset) | LINE | 주어진 방향(direction)으로 오프셋(offset)만큼 떨어진, 원본 LINE 객체와 평행한 라인을 반환한다. |
| **Overlap**(LINE other) | LINE | 두 평행한 라인의 중첩된 라인을 반환한다. 모든 위치는 원본 객체에 투영되어 반환된다. |
| **Union**(LINE other) | LINE | LINE과 다른 라인(other)의 합집합을 반환한다. 두 라인은 평행해야 하며, 모든 위치는 원본 객체에 투영되어 반환된다. |