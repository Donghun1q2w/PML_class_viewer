---
tags: [PML2, E3D, Gadget, Form, Numeric]
aliases: [NUMERICINPUT Object]
classification: Forms and Menu Objects & Gadgets
---

# [[NUMERICINPUT]]

## 개요
NumericInput 가젯은 지정된 입도(granularity)로 지정된 범위 내에서 숫자 입력을 허용한다. 위/아래 화살표는 지정된 증분값만큼 표시된 값을 증가시키거나 감소시키며, 직접 값을 입력할 수도 있다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **val** | [[REAL\|REAL Object]] | 숫자 입력 값. 범위 내에서 가장 가까운 값으로 조정된다. |
| **range** | REAL ARRAY | 범위: 시작값, 종료값, 증분값(\u003e0)을 실수로 정의한다. |
| **ndp** | [[REAL\|REAL Object]] | 표시될 소수점 자릿수의 정수값(Readonly). 0은 정수 값을 의미한다. |
| **modifiedEvents** | [[BOOLEAN\|BOOLEAN Object]] | modified 이벤트 활성화/비활성화. |
| **editable** | [[BOOLEAN\|BOOLEAN Object]] | 표시된 값의 편집 활성화/비활성화. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **setRange** (!range, !ndp) | NO RESULT | 범위와 소수점 자릿수를 설정한다. !range는 최소값, 최대값, 증분값(\u003e0)을 정의하는 REAL 배열이다. !NDP가 0보다 작으면 현재 값을 변경하지 않는다. |

## 커맨드 (Commands)
```pml
.-------\u003c-------------------.
/                           |
-- NUMERICinput gname -+- \u003cfgtagw\u003e ------------------|
                       +- \u003cfgpos\u003e -------------------|
                       +- \u003cfganch\u003e ------------------|
                       +- \u003cfgdock\u003e ------------------|
                       +- CALLback text -------------|
                       +- TOOLTIP text --------------|
                       +- CORE ----------------------* Core managed gadget
                       |-.-------\u003c-------------------.
                       |/                            |
                       +- RANGE val val -------------|
                       +- STEP val ------------------|
                       +- NDP int -------------------*
                       |
                       +- VALUE val -.
                       '-------------'- \u003cvwid\u003e -+- TOOLTIP text -. 
                                        '--------------'--\u003e
```

## 노트 (Notes)
1. 태그 텍스트가 표시된다.
2. 기본 초기값은 범위의 최소값이다.
3. 범위 최대값은 스텝(증분)의 정수배가 되도록 조정된다.
4. NDP는 소수점 자릿수이다. NDP가 0이면 모든 값은 정수가 된다.
5. 입력된 값은 범위 내에서 가장 가까운 유효한 값으로 조정된다.
6. `\u003cvwid\u003e` 그래프를 통해 가젯 너비를 구체적으로 설정하거나 폼의 다른 가젯과 관련하여 설정할 수 있다.
7. 가젯에 표시되는 값에 대해 사용자 지정 서식을 제공할 수 없다.