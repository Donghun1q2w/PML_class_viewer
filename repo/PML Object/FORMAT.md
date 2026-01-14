---
tags: [PML2, E3D, Formatting, Units, StringConversion]
aliases: [FORMAT Object]
classification: Formatting Text
---

# [[FORMAT]]

## 개요
FORMAT 오브젝트는 실수(real) 오브젝트, 특히 거리와 같은 물리적 실수 오브젝트의 출력을 서식화하는 데 사용됩니다. 이 오브젝트는 정밀도, 단위, 변환 및 단위 한정자(unit qualifiers)를 제어합니다. 또한 사용자 인터페이스의 텍스트 상자나 실수-문자열 변환 메소드에서 문자열을 실수로 변환할 때 차원(dimensions)과 단위에 대한 지침을 제공하는 데에도 사용됩니다.

## 멤버 (Members)

| Name              | Type    | Purpose                                                                                                                                                                                           |
| :---------------- | :------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **CompSeparator** | STRING  | 다중 구성요소 데이터 타입(예: POSITIONS)에 사용되는 구분 기호입니다. (기본값 SPACE)                                                                                                                                          |
| **Denominator**   | REAL    | 야드파운드법(Imperial) 분수의 최대 분모입니다. (기본값 32)                                                                                                                                                           |
| **Dimension**     | STRING  | 숫자의 차원을 설정합니다. 'NONE'(기본값/무차원), 'L'(길이), 'L2'(면적), 'L3'(부피). TYPE 문자열은 기존 값(L, L2, L3, NONE), 표준 차원(예: Measure), 또는 표준 단위(전체 이름, 설명, 단축명, 복합 단위 한정자 등)일 수 있습니다. 형식이 사용될 때까지 실제 유효성 검사는 수행되지 않습니다. |
| **DP**            | REAL    | 10진수 소수의 소수점 자릿수입니다. (기본값 2)                                                                                                                                                                      |
| **ENU**           | [[BOOLEAN\|BOOLEAN Object]] | POSITIONS 출력 시 ENU 형식을 사용할지 여부입니다. (기본값 TRUE). FALSE일 경우 XYZ 형식을 사용합니다.                                                                                                                           |
| **Fraction**      | [[BOOLEAN\|BOOLEAN Object]] | 소수 부분을 10진수로 출력할지(FALSE, 기본값), 분수로 출력할지(TRUE) 결정합니다.                                                                                                                                              |
| **FtLabel**       | STRING  | 피트(feet)에 사용되는 라벨입니다. 예: ' 또는 FT 또는 ft 또는 feet. (기본값 ‘)                                                                                                                                           |
| **InchSeparator** | STRING  | 인치와 분수 사이의 구분 기호입니다. (기본값 .)                                                                                                                                                                      |
| **Label**         | STRING  | 일반적인 거리 라벨입니다. 예: mm, m, " 또는 IN (기본값은 라벨 없음). 라벨이 UNITS로 설정되면 형식의 차원과 일치하는 표준 단위 한정자가 시스템에 의해 출력됩니다.                                                                                             |
| **PadFractions**  | [[BOOLEAN\|BOOLEAN Object]] | 분수를 후행 공백으로 채울지 여부입니다. (기본값 FALSE: 채우지 않음)                                                                                                                                                        |
| **TrailZeros**    | [[BOOLEAN\|BOOLEAN Object]] | TrailZeros가 설정되지 않거나 TRUE인 경우, 필요한 소수 자릿수(DP 멤버로 설정됨)까지 후행 0이 포함됩니다. FALSE인 경우 후행 소수점을 포함하여 후행 0이 제거됩니다.                                                                                          |
| **Units**         | STRING  | 숫자를 밀리미터(MM - 기본값), 미터(M), 피트와 인치(FINCH), 인치(INCH)로 출력합니다. TYPE 문자열은 단위의 표준 형식이나 복합 단위일 수 있습니다. 형식이 사용될 때까지 이 문자열에 대한 유효성 검사는 수행되지 않으며, 사용 시 값이 지정된 단위로 변환됩니다.                                    |
| **OriginExp**     | BLOCK   | 좌표의 기준입니다. World 기준(\|\|, ''), 또는 Current Element 기준(\|CE\|).                                                                                                                                     |
| **Zeros**         | [[BOOLEAN\|BOOLEAN Object]] | 야드파운드법 단위에 대해 선행 0(Leading zeroes)을 표시할지 여부입니다. (기본값 TRUE: 표시함, FALSE: 표시하지 않음)                                                                                                                   |