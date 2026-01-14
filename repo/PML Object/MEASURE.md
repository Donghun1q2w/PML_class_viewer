---
tags: [PML2, E3D, Measure, Dimension, Unit]
aliases: [MEASURE Object]
classification: PML Built-in Objects
---

# [[MEASURE]]

## 개요
MEASURE 객체는 유효하지 않거나 설정되지 않은 차원(dimension)을 생성하거나, 설명, 이름, 해시코드, 형식 코드 등과 일치하는 문자열을 기반으로 차원을 생성하는 데 사용된다. 또한 유효한 열거형(enum) 값이나 비표준 차원 값을 나타내는 실수를 사용하여 객체를 생성할 수도 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Measure** () | MEASURE | 유효하지 않거나 설정되지 않은(INVALID) 차원을 생성한다. |
| **Measure** (STRING) | MEASURE | 설명(description), 이름(name), 해시코드(hashcode), 형식 코드(format code) 또는 측정 단위의 인식 가능한 이름이나 약어와 일치하는 문자열로 MEASURE 객체를 생성한다. |
| **Measure** (REAL) | MEASURE | REAL 값이 (유효한) 열거형 값이거나 음수(비표준) 차원인 경우 MEASURE 객체를 생성한다. |
| **Description** () | [[STRING\|STRING Object]] | 차원의 긴 설명(Long description)을 반환한다. |
| **String** () | [[STRING\|STRING Object]] | 차원의 긴 설명(Long description)을 반환한다. |
| **Name** () | [[STRING\|STRING Object]] | 형식 문(format statements) 및 명령(commands)에 사용되는 고유한 이름이다. |
| **Hashcode** () | [[STRING\|STRING Object]] | 차원의 해시 코드이다. 표준 차원이 아닌(generic) 경우 'GENERIC'을 반환한다. |
| **Ptype** () | [[STRING\|STRING Object]] | 차원의 해시 코드이다. 표준 차원이 아닌(generic) 경우 'GENERIC'을 반환한다. |
| **currentunits** () | UNIT | 이 차원의 현재 단위(current unit)를 반환한다. |
| **UnitQualifier** () | [[STRING\|STRING Object]] | 현재 단위의 단위 한정자(unit qualifier)를 반환한다. |
| **UnitFactor** () | [[REAL\|REAL Object]] | 현재 단위에서 데이터베이스 단위로의 변환 계수(conversion factor)를 반환한다. |
| **SetUnits** (unit) | [[BOOLEAN\|BOOLEAN Object]] | 차원의 현재 단위를 unit으로 성공적으로 설정하면 TRUE를 반환한다. |
| **Numeric** () | [[BOOLEAN\|BOOLEAN Object]] | 차원의 현재 단위를 Numeric(단위 변환 없음)으로 설정한다. NUMERIC 단위는 Hashcode가 NUMB이며 이름, 단위 한정자, 설명이 없다. 성공하면 TRUE를 반환한다. |
| **Default** () | [[BOOLEAN\|BOOLEAN Object]] | 모든 차원의 현재 단위를 카탈로그 BUNI/DUNI에 정의된 것으로 설정한다. 성공하면 TRUE를 반환한다. |
| **Suspend** () | [[BOOLEAN\|BOOLEAN Object]] | 모든 물리량(physical quantities)의 현재 단위를 일시 중단하고 데이터베이스 단위로만 독점적으로 작동한다. 중단 레벨을 한 단계 올린다. 성공하면 TRUE를 반환한다. |
| **SuspendLevel** () | [[REAL\|REAL Object]] | 현재 단위의 중단(suspension) 레벨 수를 반환한다. 중단 상태가 아니면 0이다. |
| **Reinstate** () | [[BOOLEAN\|BOOLEAN Object]] | 모든 수량에 대해 정의된 현재 작업 단위를 복원한다. 중단 스택(suspension stack)을 지운다. 성공하면 TRUE를 반환한다. |
| **Unsuspend** () | [[BOOLEAN\|BOOLEAN Object]] | 현재 단위의 중단 스택에서 한 레벨을 꺼낸다(pop). 레벨이 1이 되면 정의된 현재 단위로 작업한다. 성공하면 TRUE를 반환한다. |
| **IsNull** () | [[BOOLEAN\|BOOLEAN Object]] | 차원이 NONE이면 TRUE를 반환한다. |
| **IsStandard** () | [[BOOLEAN\|BOOLEAN Object]] | 차원이 명명된(표준) 차원이면 TRUE를 반환한다. 기본 구성요소의 거듭제곱으로 지정된 경우(Generic) FALSE를 반환한다. |