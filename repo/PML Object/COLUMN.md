---
tags: [PML2, E3D, Table, Report, Collection]
aliases: [COLUMN Object]
classification: Collection and Report Objects
---

# [[COLUMN]]

## 개요
COLUMN Object는 Table Object의 열(column)이 채워지는 방식을 정의한다. 열의 서식(formatting)은 열 정의 자체와 분리되어 Table Object에서 데이터를 추출하는 Report Object 내에 유지되어야 하며, 이를 통해 Table을 재생성하지 않고도 동일한 Table에서 다양한 리포트를 생성할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Column**() | | 생성자 (모든 객체 설정을 초기화함) |
| **Column**(EXPRESSION, BOOLEAN, BOOLEAN, STRING) | | Expression, Sort, Ascending, Key를 설정하는 생성자 |
| **Key** (STRING) | | 키를 설정하고 대문자로 강제 변환함 |
| **Expression** (EXPRESSION) | | 열을 채우는 데 사용되는 표현식을 정의함 |
| **Sort**() | | 열 정렬(sort)을 켬 |
| **NoSort**() | | 열 정렬을 끔 (기본 설정) |
| **Ascending**() | | 열 정렬을 오름차순으로 설정함 |
| **Descending**() | | 열 정렬을 내림차순으로 설정함 |
| **Key**() | [[STRING\|STRING Object]] | 리포팅 시 사용할 키워드를 반환함 |
| **Expression**() | EXPRESSION | 열의 내용을 도출하는 데 사용된 표현식을 반환함 |
| **IsSorted**() | [[BOOLEAN\|BOOLEAN Object]] | 열이 정렬되어 있으면 TRUE를 반환함 |
| **SortType**() | [[STRING\|STRING Object]] | 열 정렬 설정(ascending, descending, 또는 off)을 반환함 |