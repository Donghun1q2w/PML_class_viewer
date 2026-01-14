---
tags: [PML2, E3D, Geometry, Vector]
aliases: [DIRECTION Object]
classification: 3D Geometry Objects
---

# [[DIRECTION]]

## 개요
Direction(방향) Object는 월드(World) 또는 데이터베이스 요소의 참조 프레임(frame of reference) 내에 정의된 3D 벡터이다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **East** | [[REAL\|REAL Object]] | Origin 요소의 참조 프레임 내 EAST 또는 X 성분 방향 벡터 |
| **North** | [[REAL\|REAL Object]] | Origin 요소의 참조 프레임 내 NORTH 또는 Y 성분 방향 벡터 |
| **Up** | [[REAL\|REAL Object]] | Origin 요소의 참조 프레임 내 UP 또는 Z 성분 방향 벡터 |
| **Origin** | [[dbref\|dbref Object]] | 참조 프레임 DIRECTION을 정의하는 원점(origin)인 DB 요소 |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Direction** ( STRING ) | [[Direction\|Direction Object]] | STRING으로 주어진 값을 사용하여 DIRECTION 생성 |
| **Direction** ( STRING, FORMAT ) | [[Direction\|Direction Object]] | 지정된 FORMAT 형식의 STRING으로 주어진 값을 사용하여 DIRECTION 생성 |
| **EQ** ( DIRECTION ) | [[BOOLEAN\|BOOLEAN Object]] | 두 방향이 같으면 TRUE 반환 |
| **LT** ( DIRECTION ) | [[BOOLEAN\|BOOLEAN Object]] | 방향이 인자보다 작으면 TRUE 반환 |
| **String** ( FORMAT ) | [[STRING\|STRING Object]] | STRING으로 변환 |
| **WRT** ( DBREF ) | [[Direction\|Direction Object]] | 주어진 요소에 대해 새로운 DIRECTION으로 변환 |
| **Angle** ( DIRECTION ) | [[REAL\|REAL Object]] | 두 방향 사이의 각도 반환 |
| **Bisect** ( DIRECTION ) | [[Direction\|Direction Object]] | 두 방향 사이의 중간 방향 반환 |
| **Cross** ( DIRECTION ) | [[Direction\|Direction Object]] | 두 방향의 외적(cross product) 반환 |
| **Dot** ( DIRECTION ) | [[REAL\|REAL Object]] | 두 방향의 내적(dot product) 반환 |
| **IsParallel** ( DIRECTION ) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 방향들이 평행하면 TRUE, 그렇지 않으면 FALSE 반환 |
| **IsParallel** ( DIRECTION, REAL ) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 허용오차(tolerance)에 따라 방향들이 평행하면 TRUE, 그렇지 않으면 FALSE 반환 |
| **Opposite** () | [[Direction\|Direction Object]] | 반대 방향 반환 |
| **Orthogonal** ( DIRECTION ) | [[Direction\|Direction Object]] | 두 방향 사이의 직교 방향 반환 |
| **Projected** ( PLANE ) | [[Direction\|Direction Object]] | 전달된 평면에 투영된 방향 반환 |
| **IsPerpendicular** ( DIRECTION ) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 방향들이 수직이면 TRUE, 그렇지 않으면 FALSE 반환 |
| **IsPerpendicular** ( DIRECTION, REAL ) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 허용오차(tolerance)에 따라 방향들이 수직이면 TRUE, 그렇지 않으면 FALSE 반환 |

## 노트 (Notes)
- 이 메소드들 중 어느 것도 원본 객체를 수정하지 않는다.