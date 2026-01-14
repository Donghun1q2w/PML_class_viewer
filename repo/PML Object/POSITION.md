---
tags: [PML2, E3D, PDMS, Geometry, Coordinates]
aliases: [POSITION Object]
classification: PDMS Objects
---

# [[POSITION]]

## 개요
East, North, Up 좌표 성분과 원점(Origin)이 되는 DB 요소를 포함하는 객체이다. 주어진 좌표 문자열이나 포맷을 사용하여 생성할 수 있으며, 위치 간의 거리, 각도, 방향 등을 계산하거나 새로운 위치를 도출하는 다양한 기능을 제공한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **East** | [[REAL\|REAL Object]] | East(동쪽) 성분 |
| **North** | [[REAL\|REAL Object]] | North(북쪽) 성분 |
| **Up** | [[REAL\|REAL Object]] | Up(위쪽) 성분 |
| **Origin** | [[dbref\|dbref Object]] | 원점(origin)인 DB 요소 |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Position** (STRING) | [[position\|position Object]] | STRING에 주어진 좌표로 POSITION을 생성한다. |
| **Position** (STRING, FORMAT) | [[position\|position Object]] | 지정된 FORMAT을 사용하여 STRING에 주어진 좌표로 POSITION을 생성한다. |
| **Component** (DIRECTION) | [[REAL\|REAL Object]] | 지정된 DIRECTION(방향)에서의 성분 크기. |
| **EQ** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | POSITION들이 동일하면 TRUE. |
| **LT** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | POSITION이 인자보다 작으면 TRUE. |
| **String** (FORMAT) | [[STRING\|STRING Object]] | POSITION을 STRING으로 변환한다. |
| **WRT** (DBREF) | [[position\|position Object]] | 주어진 DB 요소에 대해 새로운 POSITION으로 변환한다. |
| **Angle** (POSITION, POSITION) | [[REAL\|REAL Object]] | position 객체를 중심으로 전달된 두 지점 사이의 각도를 반환한다. |
| **ArcCentre** (POSITION, POSITION, POSITION, DIRECTION, REAL) | ARC | 호 중심(arc centre) 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. |
| **ArcCentre** (POSITION, POSITION, POSITION, DIRECTION, REAL) | ARC | 호 중심(arc centre) 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. 전체 설명은 다이어그램을 참조하시오. |
| **ArcFillet** (POSITION, POSITION, DIRECTION, REAL) | ARC | 호 중심(arc centre) 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. 전체 설명은 다이어그램을 참조하시오. |
| **ArcRadius** (POSITION, POSITION, DIRECTION, REAL, BOOLEAN) | ARC | 호 반경(arc radius) 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. 부울(boolean) 값은 단호(FALSE) 또는 장호(TRUE)를 선택한다. 전체 설명은 다이어그램을 참조하시오. |
| **ArcThru** (POSITION, POSITION, DIRECTION) | ARC | 3점 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. 전체 설명은 다이어그램을 참조하시오. |
| **ArcThru** (POSITION, POSITION, DIRECTION, REAL) | ARC | 3점 및 반경 기법을 사용하여 호(arc)를 반환한다. 방향은 'normal viewing' 방향이다. 전체 설명은 다이어그램을 참조하시오. |
| **Arc3Lines** (LINE, LINE, LINE, DIRECTION) | ARC | 3개의 선 접점(line tangent points)을 통과하는 원을 반환한다. 'this' 위치는 원이 놓이는 구역(zone)을 참조한다. |
| **Direction** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 위치와 제공된 위치 사이의 방향을 반환한다. |
| **Distance** (ARC) | [[REAL\|REAL Object]] | 위치와 전달된 호(arc) 정의의 호 라인(arc line) 상 가장 가까운 지점 사이의 거리를 반환한다. |
| **MidPoint** (POSITION) | [[position\|position Object]] | 두 위치 사이의 중간 지점을 반환한다. |
| **Near** (POSITION, REAL) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치가 position 객체로부터 전달된 거리 내에 있으면 TRUE를 반환한다. |
| **Offset** (DIRECTION, REAL) | [[position\|position Object]] | 제공된 방향으로 제공된 길이만큼 오프셋된 위치를 반환한다. |
| **Plane** (POSITION, POSITION) | PLANE | 제공된 각 점이 놓여 있는 평면을 반환한다. |
| **Distance** (LINE) | [[REAL\|REAL Object]] | 위치와 전달된 무한 선(infinite line) 정의 상 가장 가까운 지점 사이의 거리를 반환한다. |
| **Distance** (PLANE) | [[REAL\|REAL Object]] | 위치와 전달된 평면(plane) 정의 상 가장 가까운 지점 사이의 거리를 반환한다. |
| **Distance** (POSITION) | [[REAL\|REAL Object]] | 두 위치 사이의 거리를 반환한다. |
| **Line** (POSITION) | LINE | position 객체에서 시작하여 두 위치 사이의 선을 반환한다. |