---
tags: [PML2, E3D, Geometry, 3D, LINE]
aliases: [LINE Object]
classification: 3D Geometry Objects
---

# [[LINE]]

## 개요
LINE 객체는 두 위치(Position) 사이의 선을 정의하는 3D 기하학 객체입니다. POINTVECTOR 객체와 관련이 있습니다.

## 멤버 (Members)
| Name | Type | Purpose |
| :--- | :--- | :--- |
| **StartPosition** | [[position\|position Object]] | 선의 시작 위치. |
| **EndPosition** | [[position\|position Object]] | 선의 끝 위치. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Line** (POSITION first, POSITION second) | LINE | 주어진 위치 first와 second 사이에 LINE을 생성한다. |
| **String** () | [[STRING\|STRING Object]] | 선을 문자열(STRING)로 반환한다. |
| **Direction** () | [[Direction\|Direction Object]] | 선의 방향을 나타내는 DIRECTION을 반환한다. |
| **Direction** (DIRECTION way) | LINE | 동일한 시작 위치와 길이를 가지지만 way에 의해 주어진 방향을 가진 새로운 선을 생성한다. |
| **On** (POSITION where) | [[BOOLEAN\|BOOLEAN Object]] | where가 무한한 선 위에 놓여 있으면 TRUE를 반환한다. |
| **On** (POSITION where, BOOLEAN bounded) | [[BOOLEAN\|BOOLEAN Object]] | where가 선 위에 놓여 있으면 TRUE를 반환하며, bounded는 점이 제한된 선분 위에 있는지도 확인할지 여부를 나타낸다. |
| **OnProjected** (POSITION where) | [[BOOLEAN\|BOOLEAN Object]] | where가 선에 투영되었을 때 제한된 선분 내에 놓이면 TRUE를 반환한다. |
| **Intersection** (LINE other) | [[position\|position Object]] | 전달된 LINE과 선 정의의 교차점을 반환한다. |
| **Intersection** (POINT point, VECTOR vector) | [[position\|position Object]] | 전달된 POINTVECTOR와 선 정의의 교차점을 반환한다. |
| **Intersection** (PLANE plane) | LINE | 평면과 선 정의의 교차 선을 반환한다. |
| **Intersections** (ARC arc) | ARRAY OF POSITIONS | 선 정의 상에서 호(arc)와의 교차점들을 반환한다. |
| **Near** (POSITION position) | [[position\|position Object]] | position에 대해 선 정의 상에서 가장 가까운 위치를 반환한다. |
| **Proportion** (REAL proportion) | [[position\|position Object]] | StartPosition으로부터 제한된(bounded) 선을 따라 proportion 비율에 위치한 지점을 반환한다. 1보다 큰 값은 선의 끝을 벗어난 위치를, 0보다 작은 값은 선의 시작을 벗어난 위치를 반환한다. |
| **Length** () | [[REAL\|REAL Object]] | 선의 길이를 반환한다. |
| **Distance** (LINE other) | [[REAL\|REAL Object]] | 선 정의와 other 사이의 최소 거리를 반환한다. |
| **Distance** (POSITION position) | [[REAL\|REAL Object]] | 선 정의와 position 사이의 최소 거리를 반환한다. |
| **Plane** () | PLANE | 선 객체의 StartPosition과 Direction을 사용하여 평면 객체를 반환한다. |
| **Pointvector** () | POINTVECTOR | 선 객체의 StartPosition과 Direction을 사용하여 POINTVECTOR 객체를 반환한다. |
| **SetLengthStart** (REAL length) | LINE | 원래의 StartPosition과 방향을 유지하면서, length에 맞는 EndPosition을 가진 새로운 선을 반환한다. |
| **SetLengthEnd** (REAL length) | LINE | 원래의 EndPosition과 방향을 유지하면서, length에 맞는 StartPosition을 가진 새로운 선을 반환한다. |
| **Towards** (POSITION position) | LINE | 원래 선과 동일한 StartPosition과 상대적 EndPosition(길이)을 가지지만, 방향이 시작 위치에서 position을 향하는 새로운 선 객체를 반환한다. |
| **From** (POSITION position) | LINE | StartPosition이 position으로 설정되고 원래의 EndPosition은 유지되는 선을 반환한다. |
| **To** (POSITION position) | LINE | EndPosition이 position으로 설정되고 원래의 StartPosition은 유지되는 선을 반환한다. |
| **ExtendStart** (REAL distance) | LINE | StartPosition이 선의 반대 방향으로 distance만큼 확장된 새로운 LINE을 반환한다. |
| **ExtendEnd** (REAL distance) | LINE | EndPosition이 선의 방향으로 distance만큼 확장된 새로운 LINE을 반환한다. |
| **ExtendStart** (PLANE plane) | LINE | StartPosition이 plane까지 확장된 새로운 LINE을 반환한다. |
| **ExtendEnd** (PLANE plane) | LINE | EndPosition이 plane까지 확장된 새로운 LINE을 반환한다. |
| **ReverseSense** () | LINE | StartPosition과 EndPosition이 서로 바뀐 선을 반환한다. |
| **Projected** (PLANE plane) | LINE | plane 위로 정규화된 LINE 정의를 반환한다. |
| **Parallel** (POSITION position) | LINE | position을 통과하며 선 객체의 선 정의와 평행한 선을 반환한다. 다른 모든 멤버는 복사된다. |
| **Offset** (DIRECTION direction, REAL offset) | LINE | 주어진 방향으로 원래 선에서 offset만큼 떨어진 LINE 객체와 평행한 선을 반환한다. |
| **Overlap** (LINE other) | LINE | 두 평행선의 겹치는 선을 반환한다. 모든 위치는 원래 객체에 투영되어 반환된다. |
| **Union** (LINE other) | LINE | LINE과 other의 합집합을 반환한다. 두 선은 평행선이며, 모든 위치는 원래 객체에 투영되어 반환된다. |