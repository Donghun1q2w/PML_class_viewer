---
tags:
  - PML2
  - E3D
  - 3D_Geometry
  - ARC
aliases:
  - ARC Object
classification: 3D Geometry Objects
---

# [[ARC]]

## 개요
ARC Object는 3D Geometry Object 분류에 속합니다. 이 객체는 Position, Orientation, Start Angle, End Angle, Radius 등으로 정의됩니다. 기본 ARC 정의와 관련된 멤버 및 메소드를 제공하며, 원본 객체를 수정하지 않는 다양한 메소드들을 포함합니다.

## 멤버 (Members)

| Name            | Type        | Purpose                                                                                        |
| :-------------- | :---------- | :--------------------------------------------------------------------------------------------- |
| **Orientation** | [[orientation\|orientation Object]] | 호(arc)의 방향(Orientation).                                                                       |
| **Position**    | POSITION    | 호(arc)의 원점/중심(Origin/Centre).                                                                  |
| **Radius**      | REAL        | 호(arc)의 반지름.                                                                                   |
| **StartAngle**  | REAL        | X축에서 호(arc)의 시작점까지의 각도.                                                                        |
| **EndAngle**    | REAL        | X축에서 호(arc)의 끝점까지의 각도.                                                                         |
| **Sense**       | BOOLEAN     | 호(arc)의 방향(sense):\u003cbr\u003e· 0: 시계 방향(clockwise)\u003cbr\u003e· 1: 반시계 방향(anti-clockwise) |

## 메소드 (Methods)

| Name                                                       | Result     | Purpose                                                                                                                                                          |
| :--------------------------------------------------------- | :--------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Arc** (POSITION, ORIENTATION, REAL, REAL, REAL, BOOLEAN) | ARC        | 주어진 Position, Orientation, Start Angle, End Angle, Radius로 호를 생성합니다. 마지막 인자가 TRUE이면 시계 방향입니다.                                                                    |
| **String** ()                                              | STRING     | 호(arc)를 문자열(string)로 반환합니다.                                                                                                                                      |
| **StartPosition** (POSITION)                               | ARC        | 전달된 위치가 호 평면에 매핑되어 시작 각도(X축 형성)로 정의되는, 원본을 기반으로 한 새로운 호를 반환합니다.                                                                                                  |
| **EndPosition** (POSITION)                                 | ARC        | StartPosition과 동일하지만 EndAngle에 대해 적용됩니다.                                                                                                                         |
| **Through** (POSITION)                                     | ARC        | 호 평면에 매핑될 때, 반지름(전체 원의)이 전달된 위치를 통과하는 새로운 호를 반환합니다.                                                                                                              |
| **ChordHeight** (REAL)                                     | ARC        | 원본을 기반으로 하되, EndAngle이 전달된 현 높이(chord height)를 생성하는 위치에 있는 새로운 호를 반환합니다. 현 높이 \u003e 반지름 또는 현 높이 \u003c 0 인 경우 unset 객체를 반환합니다. 새로운 호는 180도보다 큰 각도를 생성해서는 안 됩니다. |
| **Chord** (REAL)                                           | ARC        | 원본 StartAngle을 유지하면서 EndAngle이 시작점으로부터 지정된 거리(Distance)에 있는 새로운 호를 반환합니다. 현 길이 \u003e 반지름 * 2 또는 \u003c 0 인 경우 unset 객체를 반환합니다.                                  |
| **Circle** ()                                              | ARC        | 호의 전체 원(full circle) 정의를 반환합니다.                                                                                                                                  |
| **Circle** (BOOLEAN)                                       | ARC        | 호의 전체 원 정의를 반환합니다. True인 경우 반시계 방향입니다.                                                                                                                           |
| **Complement** ()                                          | ARC        | 호 정의의 보각 호(원의 나머지 부분)를 반환합니다.                                                                                                                                    |
| **AnglePosition** (REAL)                                   | POSITION   | 호 위에서 X축으로부터 지정된 각도에 있는 위치를 반환합니다.                                                                                                                               |
| **AngleDirection** (REAL)                                  | DIRECTION  | 호의 중심에서 X축으로부터 주어진 각도에 있는 점을 통과하는 방향을 반환합니다.                                                                                                                     |
| **StartTangent** ()                                        | DIRECTION  | 시작 각도 라인에 접하는 호 밖으로의 방향을 반환합니다. 호의 "sense"가 사용됩니다.                                                                                                               |
| **EndTangent** ()                                          | DIRECTION  | 끝 각도 라인에 접하는 호 밖으로의 방향을 반환합니다. 호의 "sense"가 사용됩니다.                                                                                                                |
| **AngleTangent** (REAL)                                    | DIRECTION  | 전달된 각도에 접하는 방향을 반환합니다.                                                                                                                                           |
| **XYOffset** (POSITION)                                    | XYPOSITION | 호 평면에 매핑된 위치를 호 평면 원점으로부터의 XY 오프셋으로 반환합니다.                                                                                                                       |
| **Proportion** (REAL)                                      | REAL       | 호의 시작 각도에서 비율(proportion)에 해당하는 위치를 X축으로부터의 각도로 반환합니다.\u003cbr\u003eAngle = (EndAngle - StartAngle) * \u003creal\u003e + StartAngle                              |
| **Angle** ()                                               | REAL       | 호가 차지하는 각도(subtended angle)를 반환합니다.                                                                                                                              |
| **Near** (POSITION)                                        | REAL       | 전달된 위치가 호 평면에 매핑된 위치에 해당하는 X축으로부터의 각도를 반환합니다.                                                                                                                    |
| **Chord** ()                                               | REAL       | 호 정의의 시작과 끝 사이의 현 길이(chord length)를 반환합니다.                                                                                                                       |
| **Length** ()                                              | REAL       | 호 라인의 실제 길이를 반환합니다.                                                                                                                                              |
| **ChordHeight** ()                                         | REAL       | 호 라인의 현 높이(chord height)를 반환합니다.                                                                                                                                 |
| **Intersections** (LINE)                                   | REAL ARRAY | 전달된 라인(호 평면에 매핑됨)과 호에 의해 정의된 원과의 교차점을 X축으로부터의 각도로 반환합니다.                                                                                                         |
| **Intersections** (PLANE)                                  | REAL ARRAY | 전달된 평면과 호에 의해 정의된 원과의 교차점을 X축으로부터의 각도로 반환합니다.                                                                                                                    |
| **Intersections** (ARC)                                    | REAL ARRAY | 전달된 호에 의해 암시되는 원과 이 객체의 호에 의해 정의된 원과의 교차점을 X축으로부터의 각도로 반환합니다. (두 호는 동일 평면에 있어야 합니다).                                                                             |
| **Tangents** (POSITION)                                    | REAL ARRAY | 전달된 위치에서 호 원(arc circle)에 접하는 접점들을 X축으로부터의 각도로 반환합니다.                                                                                                            |
| **Tangents** (ARC)                                         | REAL ARRAY | 전달된 호 원(arc circle)에 대해 이 호 원(arc circle)에 접하는 접점들을 X축으로부터의 각도로 반환합니다.                                                                                           |
| **Split** ()                                               | REAL ARRAY | 호를 0이 아닌 개수의 세그먼트로 분할합니다.                                                                                                                                        |
| **Pole** ()                                                | POSITION   | 호의 폴(pole) 위치를 반환합니다.                                                                                                                                            |
| **On** (POSITION)                                          | BOOLEAN    | 전달된 위치가 호 라인 위에 있으면 true를 반환합니다.                                                                                                                                 |
| **OnProjected** (POSITION)                                 | BOOLEAN    | 전달된 위치가 호 라인에 투영되었을 때 호 라인 내에 있으면 true를 반환합니다.                                                                                                                   |
| **OnExtended** (POSITION)                                  | BOOLEAN    | 전달된 위치가 호 라인에 매핑되었을 때 호 라인 밖에 있으면 true를 반환합니다.                                                                                                                   |

## 노트 (Notes)
- 이 객체의 메소드들은 원본 객체를 수정하지 않습니다.
- `Intersections(ARC)` 메소드의 경우, 두 호(Arcs)는 반드시 동일한 평면에 있어야 합니다 (즉, 방향의 Z 성분 간의 각도가 0 또는 180이어야 함).