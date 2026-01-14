---
tags: [PML2, E3D, Date, Formatting]
aliases: [DATEFORMAT Object]
classification: Collection and Report Objects
---

# [[DATEFORMAT]]

## 개요
DATEFORMAT 오브젝트는 날짜 속성을 날짜 순서대로 정렬할 수 있게 하기 위해 사용된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **DateFormat** (STRING format) | - | 생성자. 포맷을 정의한다. 입력 문자열 format은 'T*D*M*Y' 형식이며, 여기서 T=시간, D=일, M=월, Y=연도이고 문자의 순서는 필요한 포맷을 나타낸다. T와 D는 선택 사항이며, 시간만 필요한 경우 H를 사용할 수 있다. *는 구분 문자이다. |
| **DateFormat** () | - | 기본 포맷을 설정한다 (‘T M D Y’, month = ‘INTEGER’, year = 2). |
| **Month** (STRING) | - | 월(month) 포맷을 설정한다. 'INTEGER', 'BRIEF' 또는 'FULL'. |
| **Year** (INT) | - | 연도(year) 포맷을 설정한다. 자릿수는 2 또는 4이다. |
| **String** (DATETIME) | [[STRING\|STRING Object]] | DATETIME 포맷의 날짜를 입력받아 지정된 포맷으로 변환한다. |
| **String** (STRING) | [[STRING\|STRING Object]] | PDMS 포맷의 날짜를 입력받아 지정된 포맷으로 변환한다. |