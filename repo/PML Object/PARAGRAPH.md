---
tags: [PML2, E3D, Geometry, Draw, 3D]
aliases: [ARC Object]
classification: 3D Geometry Objects
---

# [[ARC]]

## 개요
ARC Object는 3D 기하학 객체로, 위치(Position), 방향(Orientation), 시작 각도(Start Angle), 종료 각도(End Angle), 반경(Radius)으로 정의된다. 이 객체는 기본적으로 3D 공간 상의 호(arc) 또는 원(circle)을 표현하는 데 사용된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Orientation** | [[orientation\|orientation Object]] | 호(arc)의 방향. |
| **Position** | [[position\|position Object]] | 호(arc)의 원점/중심. |
| **Radius** | [[REAL\|REAL Object]] | 호(arc)의 반경. |
| **StartAngle** | [[REAL\|REAL Object]] | X축에서 호(arc)의 시작점까지의 각도. |
| **EndAngle** | [[REAL\|REAL Object]] | X축에서 호(arc)의 끝점까지의 각도. |
| **Sense** | [[BOOLEAN\|BOOLEAN Object]] | 호(arc)의 방향 (0: 시계 방향, 1: 반시계 방향). |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Arc** (POSITION, ORIENTATION, REAL, REAL, REAL, BOOLEAN) | ARC | 주어진 위치, 방향, 시작 각도, 종료 각도, 반경으로 호를 생성한다. 마지막 인자가 TRUE이면 시계 방향이다. |
| **String** () | [[STRING\|STRING Object]] | 호(arc)를 문자열로 반환한다. |
| **StartPosition** (POSITION) | ARC | 호의 중심에서 전달된 위치를 통과하는 각도가 X축을 형성하도록 시작 각도가 정의된, 원본을 기반으로 한 새로운 호를 반환한다. |
| **EndPosition** (POSITION) | ARC | StartPosition과 유사하지만 종료 각도에 대해 수행한다. |
| **Through** (POSITION) | ARC | 호 평면에 매핑될 때 전달된 위치를 통과하는 반경(전체 원의)을 가진 새로운 호를 반환한다. |
| **ChordHeight** (REAL) | ARC | 종료 각도가 전달된 현 높이(chord height)를 생성하는 위치에 있도록 원본을 기반으로 한 새로운 호를 반환한다. 현 높이가 반경보다 크거나 0보다 작으면 설정되지 않은(unset) 객체를 반환한다. |
| **Chord** (REAL) | ARC | 원본 시작 각도를 유지하면서, 종료 각도가 시작점에서 지정된 거리(distance)만큼 떨어져 있도록 새로운 호를 반환한다. 현 길이가 반경 * 2보다 크거나 0보다 작으면 설정되지 않은(unset) 객체를 반환한다. |
| **Circle** () | ARC | 호의 전체 원(full circle) 정의를 반환한다. |
| **Circle** (BOOLEAN) | ARC | 호의 전체 원 정의를 반환한다. True일 경우 반시계 방향이다. |
| **Complement** () | ARC | 호 정의의 보수 호(원의 나머지 부분)를 반환한다. |
| **AnglePosition** (REAL) | [[position\|position Object]] | 호 위의 지정된 각도에 있는 위치를 반환한다. |
| **AngleDirection** (REAL) | [[Direction\|Direction Object]] | 호의 중심에서 X축으로부터 주어진 각도에 있는 점을 향하는 방향을 반환한다. |
| **StartTangent** () | [[Direction\|Direction Object]] | 시작 각도 라인에 접하는(tangential) 호 밖으로의 방향을 반환한다. 호의 "sense"가 사용된다. |
| **EndTangent** () | [[Direction\|Direction Object]] | 종료 각도 라인에 접하는 호 밖으로의 방향을 반환한다. 호의 "sense"가 사용된다. |
| **AngleTangent** (REAL) | [[Direction\|Direction Object]] | 전달된 각도에 접하는 방향을 반환한다. |
| **XYOffset** (POSITION) | XYPOSITION | 호 평면 원점으로부터의 XY 오프셋으로, 호 평면에 매핑된 위치를 반환한다. |
| **Proportion** (REAL) | [[REAL\|REAL Object]] | 시작 각도로부터의 비율(proportion)에 해당하는 위치를 X축으로부터의 각도로 반환한다. Angle = (EndAngle - StartAngle) * \u003creal\u003e + StartAngle. |
| **Angle** () | [[REAL\|REAL Object]] | 호의 중심각(subtended angle)을 반환한다. |
| **Near** (POSITION) | [[REAL\|REAL Object]] | 전달된 위치를 호 평면에 매핑했을 때 X축으로부터의 각도에 해당하는 위치를 반환한다. |
| **Chord** () | [[REAL\|REAL Object]] | 호 정의의 시작과 끝 사이의 현(chord) 길이를 반환한다. |
| **Length** () | [[REAL\|REAL Object]] | 호 라인의 실제 길이를 반환한다. |
| **ChordHeight** () | [[REAL\|REAL Object]] | 호 라인의 현 높이(chord height)를 반환한다. |
| **Intersections** (LINE) | REAL ARRAY | 호에 의해 정의된 원과 전달된 라인(호 평면에 매핑됨)의 교차점을 X축으로부터의 각도로 반환한다. |
| **Intersections** (PLANE) | REAL ARRAY | 호에 의해 정의된 원과 전달된 평면의 교차점을 X축으로부터의 각도로 반환한다. |
| **Intersections** (ARC) | REAL ARRAY | 호에 의해 정의된 원과 전달된 호(arc)에 의해 암시되는 원의 교차점을 X축으로부터의 각도로 반환한다. 두 호는 반드시 같은 평면에 있어야 한다. |
| **Tangents** (POSITION) | REAL ARRAY | 전달된 위치에서 호 원(arc circle)에 접하는 접점들을 X축으로부터의 각도로 반환한다. |
| **Tangents** (ARC) | REAL ARRAY | 전달된 호 원(arc circle)에 대해 호 원에 접하는 접점들을 X축으로부터의 각도로 반환한다. |
| **Split** () | REAL ARRAY | 호를 0이 아닌 세그먼트 수로 분할한다. |
| **Pole** () | [[position\|position Object]] | 호의 극(pole) 위치를 반환한다. |
| **On** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치가 호 라인 위에 있으면 true를 반환한다. |
| **OnProjected** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치를 호 라인에 투영했을 때 그 안에 있으면 true를 반환한다. |
| **OnExtended** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치를 호 라인에 매핑했을 때 외부에 있으면 true를 반환한다. |