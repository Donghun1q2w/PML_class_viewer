---
tags: [PML2, E3D, PML_Built_in_Objects]
aliases: [BOOLEAN Object]
classification: PML Built-in Objects
---

# [[BOOLEAN]]

## 개요
PML Built-in Object 중 하나이다. 이 Object의 메소드 중 어떤 것도 원본 Object를 수정하지 않는다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **BOOLEAN** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 값이 0이 아니면 TRUE, 0이면 FALSE로 설정된 Boolean Object를 생성하는 생성자이다. |
| **BOOLEAN** (STRING value) | [[BOOLEAN\|BOOLEAN Object]] | 문자열 값에 따라 Boolean Object를 생성하는 생성자이다. (T, TR, TRU, TRUE, Y, YE, YES는 'TRUE'; F, FA, FAL, FALS, FALSE, N, NO는 'FALSE') |
| **BOOLEAN** ( STRING value, FORMAT format) | [[BOOLEAN\|BOOLEAN Object]] | 위와 동일하다. FORMAT 인자는 Forms 및 Menus와의 일관성을 위해 필요하다. |
| **AND** () | [[BOOLEAN\|BOOLEAN Object]] | 두 값이 모두 TRUE인 경우 TRUE이다. |
| **NOT** () | [[BOOLEAN\|BOOLEAN Object]] | FALSE이면 TRUE, TRUE이면 FALSE이다. |
| **OR** (BOOLEAN value) | [[BOOLEAN\|BOOLEAN Object]] | 두 값 중 하나라도 TRUE이면 TRUE이다. |
| **Real** () | [[REAL\|REAL Object]] | Boolean이 TRUE이면 1, FALSE이면 0이다. |
| **String** () | [[STRING\|STRING Object]] | Boolean이 TRUE이면 'TRUE', FALSE이면 'FALSE'이다. |