---
tags: [PML2, E3D, Date, Time]
aliases: [DATETIME Object]
classification: PML Built-in Objects
---

# [[DATETIME]]

## 개요
DATETIME 오브젝트는 날짜와 시간 정보를 생성하고 조작하는 데 사용된다. 현재 날짜와 시간을 포함하거나 특정 연도, 월, 일, 시간, 분, 초로 설정된 오브젝트를 생성할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **DateTime** () | DATETIME | 현재 날짜와 시간이 포함된 DATETIME 오브젝트를 생성한다. |
| **DateTime** (REAL year, REAL month, REAL date) | DATETIME | 주어진 연도, 월, 일로 설정된 DATETIME을 생성한다. 시간은 00:00:00으로 기본 설정된다. |
| **DateTime** (REAL year, STRING month, REAL date) | DATETIME | 위와 동일하지만, 월(month)은 ‘Jan’, ‘March’, ‘DECEM’과 같이 최소 3글자 이상의 문자열(STRING)로 표현된다. |
| **DateTime** (REAL year, REAL month, REAL date, REAL hour, REAL minute) | DATETIME | 주어진 연도, 월, 일, 시간, 분으로 설정된 DATETIME 오브젝트를 생성한다. 초는 0으로 기본 설정된다. |
| **DateTime** (REAL year, STRING month, REAL date, REAL hour, REAL minute) | DATETIME | 위와 동일하지만, 월(month)은 ‘Jan’, ‘March’, ‘DECEM’과 같이 최소 3글자 이상의 문자열(STRING)로 표현된다. |
| **DateTime** (REAL year, REAL month, REAL date, REAL hour, REAL minute, REAL second) | DATETIME | 주어진 연도, 월, 일, 시간, 분, 초로 설정된 DATETIME 오브젝트를 생성한다. |
| **DateTime** (REAL year, STRING month, REAL date, REAL hour, REAL minute, REAL second) | DATETIME | 위와 동일하지만, 월(month)은 ‘Jan’, ‘March’, ‘DECEM’과 같이 최소 3글자 이상의 문자열(STRING)로 표현된다. |
| **Date** () | [[REAL\|REAL Object]] | 이 DATETIME 오브젝트의 일(day of month)을 반환한다 (1-31). |
| **GEQ** (DATETIME) | [[BOOLEAN\|BOOLEAN Object]] | 이 DATETIME이 인자 DATETIME보다 이후이거나 같으면 테스트한다. |
| **GT** (DATETIME) | [[BOOLEAN\|BOOLEAN Object]] | 이 날짜가 인자 DATETIME보다 이후인지 테스트한다. |
| **HOUR** () | [[REAL\|REAL Object]] | 이 DATETIME 오브젝트의 시간을 REAL로 반환한다 (0-23). |
| **LEQ** (DATETIME) | [[BOOLEAN\|BOOLEAN Object]] | 이 DATETIME이 인자 DATETIME보다 이전이거나 같으면 테스트한다. |
| **LT** (DATETIME) | [[BOOLEAN\|BOOLEAN Object]] | 이 DATETIME이 인자 DATETIME보다 이전인지 테스트한다. |
| **Minute** () | [[REAL\|REAL Object]] | 이 DATETIME 오브젝트의 분을 REAL로 반환한다 (0-59). |
| **Month** () | [[REAL\|REAL Object]] | 이 DATETIME 오브젝트의 월을 REAL로 반환한다 (1-12). |
| **MonthString** () | [[STRING\|STRING Object]] | 이 DATETIME 오브젝트의 월을 STRING으로 반환한다 (‘January’, ‘February’ 등). |
| **Second** () | [[REAL\|REAL Object]] | 이 DATETIME 오브젝트의 초 수를 REAL로 반환한다 (0-59). |
| **Year** () | [[REAL\|REAL Object]] | 연도를 REAL로 반환한다 (예: 1998). |