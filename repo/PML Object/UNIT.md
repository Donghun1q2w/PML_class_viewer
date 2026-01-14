---
tags: [PML2, E3D, PML_Built_in_Objects, Unit, Measurement]
aliases: [UNIT Object]
classification: PML Built-in Objects
---

# [[UNIT]]

## 개요
UNIT Object는 PML 내장 Object(PML Built-in Objects) 중 하나이다. 이 Object는 단위(Unit)를 생성하고, 단위의 속성(이름, 설명, 차원 등)을 조회하거나 변환하는 기능을 제공한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Unit** () |  | 생성자 (초기 설정 없음). |
| **Unit** (REAL) | UNIT | REAL 값이 (유효한) enum 값이거나 음수(복합) 단위인 UNIT을 생성한다. |
| **Unit** (STRING) | UNIT | Description, Name, ComponentName, 또는 Hashcode 순서로 해당하는 문자열을 사용하여 UNIT을 생성한다. |
| **Description** () | [[STRING\|STRING Object]] | 단위(unit)에 대한 긴 설명이며, 매우 자주 Name()과 동일하다. |
| **String** () | [[STRING\|STRING Object]] | (매뉴얼상 Description()과 동일한 목적으로 기재됨) |
| **Name** () | [[STRING\|STRING Object]] | 단일 단위(solitary units)에 대한 한정자(qualifier)로 사용되는 단위 이름이다. |
| **ShortName** () | [[STRING\|STRING Object]] | 구성 요소 단위(component units)에 대한 한정자로 사용되는 짧은 이름이다. 매우 자주 Name()과 동일하다. |
| **Hashcode** () | [[STRING\|STRING Object]] | 단위의 해시 코드이다. 복합 단위(compound unit)인 경우 'COMPOUND'를 반환하고, 구성 요소 표준 단위에서 파생된 경우(예: 면적 단위는 거리의 제곱) 'DRVD'를 반환한다. |
| **Ptype** () | [[STRING\|STRING Object]] | (매뉴얼상 Hashcode()와 동일한 목적으로 기재됨) |
| **Enum** () | [[REAL\|REAL Object]] | 이 단위에 대한 고유 정수 ID이다. 표준 단위이면 양수, 복합 단위이면 음수이다. |
| **Factor** () | [[REAL\|REAL Object]] | 데이터베이스 단위로의 변환 계수이다. |
| **UnitQualifier** () | [[STRING\|STRING Object]] | 현재 단위의 단위 한정자(Unit qualifier)이다. |
| **Dimension** () | MEASURE | 단위의 차원(Dimension)이다. |
| **IsStandard** () | [[BOOLEAN\|BOOLEAN Object]] | 표준 단일 단위인 경우 TRUE이다. 복합 단위(예: kg/m3, m2)인 경우 FALSE이다. |
| **IsNull** () | [[BOOLEAN\|BOOLEAN Object]] | 단위가 NONE인 경우 TRUE이다. |
| **AllDimensions** () | ARRAY of MEASURES | 모든 표준 차원(dimensions)의 집합이다. |
| **AllUnits** () | ARRAY of UNITS | 이름이 지정된 모든 표준 단위(Units)의 집합이다. |
| **IsImperial** () | [[BOOLEAN\|BOOLEAN Object]] | 전적으로 야드파운드법(imperial) 단위(예: inch, lb)이거나 특정되지 않은 단위(예: second, ohm, degree)인 경우 TRUE이다. |
| **IsMetric** () | [[BOOLEAN\|BOOLEAN Object]] | 전적으로 미터법(metric) 단위(예: mm, kg)이거나 미터법 상황에서 사용되는 특정되지 않은 단위인 경우 TRUE이다. |

## 노트 (Notes)
- 파생 단위(현재 거리에서 파생된 면적 단위와 같이 구성 요소 차원의 현재 단위에서 파생된 단위) 및 숫자 단위(변환 또는 단위 한정자가 없음)는 이름(name), 설명(description) 및 한정자(qualifier)에 대해 빈 문자열을 갖는다. 그러나 이들의 해시 코드는 DRVD 및 NUMB이므로 `object unit ('DRVD')`와 같이 폼을 사용하여 생성할 수 있다. `measure.setUnits`를 사용하여 현재 단위를 이것으로 설정할 수 있다. 또한, `measure.numeric()`을 사용하여 숫자 현재 단위를 설정할 수 있다.