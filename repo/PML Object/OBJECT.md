---
tags: [PML2, E3D, Geometry, ARC]
aliases: [ARC Object]
classification: 3D Geometry Objects
---

# [[ARC]]

## 개요
ARC(호) 객체는 3D 공간상의 위치(Position), 방향(Orientation), 반지름(Radius), 시작 및 끝 각도를 기반으로 정의되는 기하학적 객체이다. 이 객체는 생성자 및 다양한 메소드를 통해 3D 상호작용 및 기하학적 계산에 사용된다.

## 멤버 (Members)
| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Orientation** | [[orientation\|orientation Object]] | 아크의 오리엔테이션 (방향). |
| **Position** | [[position\|position Object]] | 아크의 원점/중심 (Origin/Centre). |
| **Radius** | [[REAL\|REAL Object]] | 아크의 반지름. |
| **StartAngle** | [[REAL\|REAL Object]] | X축에서 아크 시작점까지의 각도. |
| **EndAngle** | [[REAL\|REAL Object]] | X축에서 아크 끝점까지의 각도. |
| **Sense** | [[BOOLEAN\|BOOLEAN Object]] | 아크 방향: \u003cbr\u003e· 0: 시계 방향 (clockwise)\u003cbr\u003e· 1: 반시계 방향 (anti-clockwise) |

## 메소드 (Methods)
| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Arc** (Position, Orientation, StartAngle, EndAngle, Radius, Clockwise) | ARC | 주어진 위치, 오리엔테이션, 시작 각도, 끝 각도, 반지름으로 아크를 생성한다. 마지막 인수가 TRUE이면 시계 방향이다. (생성자) |
| **String** () | [[STRING\|STRING Object]] | 아크를 문자열(STRING)로 반환한다. |
| **StartPosition** (POSITION) | ARC | 원본을 기반으로, 아크의 중심에서 전달된 위치를 통과하는 선이 아크 평면에 매핑되어 X축을 형성하도록 시작 각도가 정의된 새로운 아크를 반환한다. |
| **EndPosition** (POSITION) | ARC | StartPosition과 동일하지만 끝 각도(EndAngle)에 대해 수행한다. |
| **Through** (POSITION) | ARC | 아크 평면에 매핑될 때 전달된 위치를 통과하는 반지름(전체 원의)을 가진 새로운 아크를 반환한다. |
| **ChordHeight** (REAL) | ARC | 원본을 기반으로, 전달된 현(chord)의 높이를 생성하는 위치에 EndAngle이 오도록 하는 새로운 아크를 반환한다.\u003cbr\u003e현 높이 \u003e 반지름 또는 현 높이 \u003c 0 인 경우 설정되지 않은(unset) 객체를 반환한다.\u003cbr\u003e새로운 아크는 180도보다 큰 각도를 생성하지 않아야 한다. |
| **Chord** (REAL) | ARC | 원본의 StartAngle을 유지하면서, Start점에서 지정된 거리(Start로부터의 거리)에 EndAngle이 오도록 하는 새로운 아크를 반환한다.\u003cbr\u003e현 길이 \u003e 반지름 * 2 또는 \u003c 0 인 경우 설정되지 않은(unset) 객체를 반환한다. |
| **Circle** () | ARC | 아크 정의의 전체 원(full circle)을 반환한다. |
| **Circle** (BOOLEAN) | ARC | 아크의 전체 원 정의를 반환한다. True일 경우 아크는 반시계 방향이다. |
| **Complement** () | ARC | 아크 정의의 보충 아크(원의 나머지 부분)를 반환한다. |
| **AnglePosition** (REAL) | [[position\|position Object]] | 아크 상의 지정된 각도 위치를 반환한다. |
| **AngleDirection** (REAL) | [[Direction\|Direction Object]] | 아크의 중심에서 X축으로부터 주어진 각도에 있는 점을 통과하는 방향을 반환한다. |
| **StartTangent** () | [[Direction\|Direction Object]] | 시작 각도 라인에 접하는 아크 밖으로의 방향을 반환한다. 아크의 "Sense"가 사용된다. |
| **EndTangent** () | [[Direction\|Direction Object]] | 끝 각도 라인에 접하는 아크 밖으로의 방향을 반환한다. 아크의 "Sense"가 사용된다. |
| **AngleTangent** (REAL) | [[Direction\|Direction Object]] | 전달된 각도에 접하는 방향을 반환한다. |
| **XYOffset** (POSITION) | XYPOSITION | 아크 평면의 원점으로부터의 XY 오프셋 관점에서, 아크 평면에 매핑된 위치를 반환한다. |
| **Proportion** (REAL) | [[REAL\|REAL Object]] | 아크의 시작 각도로부터 비율(proportion)에 해당하는 위치를 X축으로부터의 각도 관점에서 반환한다.\u003cbr\u003eAngle = (EndAngle - StartAngle) * \u003creal\u003e + StartAngle |
| **Angle** () | [[REAL\|REAL Object]] | 아크의 사잇각(subtended angle)을 반환한다. |
| **Near** (POSITION) | [[REAL\|REAL Object]] | 전달된 위치가 아크 평면에 매핑된 위치에 대해, X축으로부터의 각도 관점에서의 위치를 반환한다. |
| **Chord** () | [[REAL\|REAL Object]] | 아크 정의의 시작과 끝 사이의 현(chord) 길이를 반환한다. |
| **Length** () | [[REAL\|REAL Object]] | 아크 라인의 실제 길이를 반환한다. |
| **ChordHeight** () | [[REAL\|REAL Object]] | 아크 라인의 현 높이(chord height)를 반환한다. |
| **Intersections** (LINE) | REAL ARRAY | 전달된 라인(아크 평면에 매핑됨)과 아크에 의해 정의된 원과의 교차점을 X축으로부터의 각도 관점에서 반환한다. |
| **Intersections** (PLANE) | REAL ARRAY | 전달된 평면과 아크에 의해 정의된 원과의 교차점을 X축으로부터의 각도 관점에서 반환한다. |
| **Intersections** (ARC) | REAL ARRAY | 전달된 아크가 암시하는 원과 이 아크가 정의하는 원과의 교차점을 X축으로부터의 각도 관점에서 반환한다.\u003cbr\u003e두 아크는 같은 평면에 있어야 한다. (즉, 방향의 Z 성분 사이의 각도가 0도 또는 180도여야 함). |
| **Tangents** (POSITION) | REAL ARRAY | 전달된 위치에서 아크 원(arc circle)에 대한 접점들을 X축으로부터의 각도 관점에서 반환한다. |
| **Tangents** (ARC) | REAL ARRAY | 전달된 아크 원(arc circle)에 대한 아크 원의 접점들을 X축으로부터의 각도 관점에서 반환한다. |
| **Split** () | REAL ARRAY | 아크를 0이 아닌 수의 세그먼트로 분할한다. |
| **Pole** () | [[position\|position Object]] | 아크의 극(pole) 위치를 반환한다. |
| **On** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치가 아크 라인 위에 있으면 True를 반환한다. |
| **OnProjected** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치가 아크 라인에 투영될 때, 그 투영된 점이 아크 라인 내에 있으면 True를 반환한다. |
| **OnExtended** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 전달된 위치가 아크 라인에 매핑될 때, 아크 라인 바깥에 있으면 True를 반환한다. |