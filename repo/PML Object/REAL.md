---
tags: [PML2, E3D, PML_Built_in_Objects, Numeric, Measurement]
aliases: [REAL Object]
classification: PML Built-in Objects
---

# [[REAL]]

## 개요
Real Object는 정수 및 소수(분수) 부분을 가진 숫자이며, 물리적 수량(physical quantity)을 나타낼 경우 단위를 가질 수 있습니다. Real 객체는 함수, 다른 객체의 인자, 산술 표현식에서 사용될 때 이러한 물리적 수량 상태를 보존하며, 수행되는 연산과 단위가 호환되어야 합니다. Real 객체가 생성될 때는 일반적으로 해당 수량의 현재 작업 단위(current working units)로 생성됩니다.

## 메소드 (Methods)

| Name                                                                                      | Result                      | Purpose                                                                                                        |
| :---------------------------------------------------------------------------------------- | :-------------------------- | :------------------------------------------------------------------------------------------------------------- |
| **Real** (BOOLEAN)                                                                        | [[REAL\|REAL Object]]       | 주어진 BOOLEAN 값으로 REAL을 생성합니다 (TRUE = 1, FALSE = 0).                                                             |
| **Real** (BORE)                                                                           | [[REAL\|REAL Object]]       | 주어진 BORE 값으로 REAL을 생성합니다.                                                                                      |
| **Real** (STRING)                                                                         | [[REAL\|REAL Object]]       | 주어진 STRING으로 REAL을 생성합니다. 문자열에는 REAL에 값을 부여할 숫자가 포함되어야 하며, 단위 한정자가 추가된 경우 현재 작업 단위로 변환됩니다.                     |
| **Real** (STRING, FORMAT)                                                                 | [[REAL\|REAL Object]]       | 지정된 FORMAT을 사용하여 주어진 STRING으로 REAL을 생성합니다.                                                                     |
| **Real** (REAL, UNIT)                                                                     | n/a                         | UNIT의 단위로 REAL 인자(기존 단위 무시)의 값을 가진 새로운 REAL을 생성합니다.                                                            |
| **Value** ()                                                                              | [[REAL\|REAL Object]]       | 원본과 동일한 값을 가진 차원 없는(undimensioned) real을 반환합니다.                                                                |
| **Dimension** ()                                                                          | MEASURE                     | real에 기록된 물리적 수량의 차원(측정)을 반환합니다.                                                                               |
| **Unit** () 또는 **Units** ()                                                               | UNIT                        | REAL에 저장된 수량의 측정 단위를 반환합니다.                                                                                    |
| **AllDimensions** ()                                                                      | ARRAY of MEASURES           | 모든 표준 차원(dimensions)의 집합을 반환합니다.                                                                               |
| **AllUnits** ()                                                                           | ARRAY of UNITS              | 명명된 모든 표준 단위(Units)의 집합을 반환합니다.                                                                                |
| **Cast** (UNIT)                                                                           | [[REAL\|REAL Object]]       | REAL(REAL,UNIT)과 동일합니다. UNIT 단위로 REAL 객체(기존 단위 무시)의 값을 가진 REAL을 반환합니다.                                         |
| **ConvertUnits** (STRING) 또는 **Convert** (UNIT) 또는 **ConvertUnits** (UNIT)                | [[REAL\|REAL Object]]       | 원래 단위에서 UNIT 또는 STRING 인자로 지정된 단위로 변환된 REAL을 반환합니다.                                                            |
| **DBUnits** ()                                                                            | [[REAL\|REAL Object]]       | 동일한 물리적 크기를 가지지만 데이터베이스 단위(database units)인 real을 반환합니다.                                                       |
| **CurrentUnits** ()                                                                       | [[REAL\|REAL Object]]       | 동일한 물리적 크기를 가지지만, 그 값이 현재 작업 단위(current working units)로 변환된 Real을 반환합니다.                                       |
| **CurrentUnits** (STRING) 또는 **CurrentUnits** (UNIT) 또는 **CurrentUnits** (MEASURE)        | [[REAL\|REAL Object]]       | 원본과 동일한 차원을 가지며 동일한 물리적 크기를 반영하지만, 그 값이 현재 단위(current units)로 측정된 REAL을 반환합니다. 반환된 REAL은 값만 변환되며 단위나 차원은 없습니다. |
| **ABS** ()                                                                                | [[REAL\|REAL Object]]       | 숫자의 절대값을 반환합니다.                                                                                                |
| **ACos** ()                                                                               | [[REAL\|REAL Object]]       | 숫자의 아크 코사인(arc cosine) 값을 도(degrees) 단위로 반환합니다.                                                                |
| **ALog** ()                                                                               | [[REAL\|REAL Object]]       | 숫자의 지수 함수(자연 로그의 역함수) 값을 반환합니다.                                                                                |
| **ASin** ()                                                                               | [[REAL\|REAL Object]]       | 숫자의 아크 사인(arc sine) 값을 도(degrees) 단위로 반환합니다.                                                                   |
| **ATan** ()                                                                               | [[REAL\|REAL Object]]       | 숫자의 아크 탄젠트(arc tangent) 값을 도(degrees) 단위로 반환합니다.                                                               |
| **ATanT** (REAL)                                                                          | [[REAL\|REAL Object]]       | number1/number2의 아크 탄젠트 값을 적절한 부호와 함께 도(degrees) 단위로 반환합니다.                                                    |
| **Between** (REAL, REAL)                                                                  | [[BOOLEAN\|BOOLEAN Object]] | 값이 지정된 범위(지정된 값 포함) 내에 있으면 TRUE를 반환합니다. 모든 실수(reals)는 동일하거나 호환되는 물리적 수량이어야 합니다.                                |
| **Boolean** ()                                                                            | [[BOOLEAN\|BOOLEAN Object]] | 값이 0이면 FALSE, 그렇지 않으면 TRUE를 반환합니다.                                                                             |
| **Bore** ()                                                                               | BORE                        | 현재 BORE 단위에 따라 BORE로 변환합니다(정확해야 함).                                                                            |
| **Cosine** ()                                                                             | [[REAL\|REAL Object]]       | 숫자의 코사인 값을 반환합니다(도 단위로 간주됨). 실수는 각도(angle)이거나 순수 숫자여야 합니다.                                                     |
| **Distance** ()                                                                           | [[STRING\|STRING Object]]   | 기본 설정을 사용하여 거리(distance)로 변환합니다.                                                                               |
| **Distance** (BOOLEAN feet, BOOLEAN us, BOOLEAN fraction, REAL precision, BOOLEAN zeroes) | [[STRING\|STRING Object]]   | 거리를 텍스트로 변환합니다 (피트/인치, US 형식, 분수/소수, 정밀도, 0 표시 여부 등의 옵션 사용).                                                   |
| **EQ** (BORE)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 비교합니다. 두 실수는 호환되는 수량이어야 하며 일관된 단위로 비교됩니다.                                                     |
| **EQ** (REAL)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 값이 같으면 TRUE를 반환합니다.                                                                                            |
| **GEQ** (BORE)                                                                            | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 비교합니다.                                                                                        |
| **GEQ** (REAL)                                                                            | [[BOOLEAN\|BOOLEAN Object]] | 다른 값보다 크거나 같으면 TRUE를 반환합니다.                                                                                    |
| **GT** (BORE)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 비교합니다.                                                                                        |
| **GT** (REAL)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 다른 값보다 크면 TRUE를 반환합니다.                                                                                         |
| **INT** ()                                                                                | [[REAL\|REAL Object]]       | 내림(rounding down)하여 정수 값으로 변환합니다.                                                                              |
| **LEQ** (BORE)                                                                            | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 비교합니다.                                                                                        |
| **LEQ** (REAL)                                                                            | [[BOOLEAN\|BOOLEAN Object]] | 다른 값보다 작거나 같으면 TRUE를 반환합니다.                                                                                    |
| **LOG** ()                                                                                | [[REAL\|REAL Object]]       | 숫자의 자연 로그 값을 반환합니다.                                                                                            |
| **LT** (BORE)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 비교합니다.                                                                                        |
| **LT** (REAL)                                                                             | [[BOOLEAN\|BOOLEAN Object]] | 다른 값보다 작으면 TRUE를 반환합니다.                                                                                        |
| **MODULO** (REAL)                                                                         | [[REAL\|REAL Object]]       | 주어진 REAL에 대한 나머지(MODULO)를 반환합니다.                                                                               |
| **NearestBore** ()                                                                        | BORE                        | 현재 BORE 단위 설정에 따라 가장 가까운 BORE로 변환합니다.                                                                          |
| **Nint** ()                                                                               | [[REAL\|REAL Object]]       | 가장 가까운 정수(반올림)로 변환합니다.                                                                                         |
| **Power** (REAL)                                                                          | [[REAL\|REAL Object]]       | 값을 거듭제곱(power)합니다. 원래 실수가 물리적 수량인 경우 지수 값은 정수여야 합니다.                                                           |
| **Real** ()                                                                               | [[REAL\|REAL Object]]       | REAL로 변환합니다(이 경우 아무 작업도 수행하지 않음).                                                                              |
| **SBetween** (REAL, REAL)                                                                 | [[BOOLEAN\|BOOLEAN Object]] | 값이 지정된 범위(지정된 값 제외) 내에 있으면 TRUE를 반환합니다.                                                                        |
| **Sine** ()                                                                               | [[REAL\|REAL Object]]       | 숫자의 사인 값을 반환합니다(도 단위로 간주됨).                                                                                    |
| **Sqrt** ()                                                                               | [[REAL\|REAL Object]]       | 값의 제곱근을 반환합니다. 결과가 지원되는 측정 단위가 아니면 오류가 발생합니다.                                                                  |
| **String** (STRING precision)                                                             | [[STRING\|STRING Object]]   | 'D0'에서 'D6' 범위의 STRING으로 지정된 정밀도로 STRING으로 변환합니다.                                                              |
| **String** (FORMAT)                                                                       | [[STRING\|STRING Object]]   | 전역 FORMAT 객체의 설정을 사용하여 STRING으로 변환합니다.                                                                         |
| **Tangent** ()                                                                            | [[REAL\|REAL Object]]       | 숫자의 탄젠트 값을 반환합니다(도 단위로 간주됨).                                                                                   |