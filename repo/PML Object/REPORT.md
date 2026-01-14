---
tags: [PML2, E3D, Report, Table, Formatting, Collection]
aliases: [REPORT Object]
classification: Collection and Report Objects
---

# [[REPORT]]

## 개요
REPORT 오브젝트는 TABLE 오브젝트 데이터를 화면, 폼(Form) 또는 파일로 표시하기 위해 포맷팅하는 데 사용된다. 테이블 데이터의 추출과 포맷팅을 분리함으로써, 동일한 기본 테이블에서 다양한 리포트를 생성할 수 있다. 리포트는 TABLE에서 데이터를 추출하고 연관된 COLUMNFORMAT 오브젝트에 따라 각 컬럼을 포맷하며, 선택적으로 지정된 MATCH 문자열을 포함하는 행만 리포트 출력에 포함하도록 지정할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Report**() | | 생성자. |
| **Report**(TABLE) | | 테이블과 컬럼 포맷도 설정하는 생성자. |
| **Table**(TABLE) | | 리포트에 사용될 테이블을 설정한다. |
| **AddColumn**(STRING key, COLUMNFORMAT, STRING heading) | | 지정된 키(key)를 가진 컬럼을 전달된 컬럼 포맷과 함께 리포트에 추가한다. 인자 heading은 컬럼 헤딩이다. |
| **NextEntriesIndex**(REAL position) | | 다음 평가(evaluation)에 사용될 결과 배열의 위치를 설정한다. |
| **NextEntriesIndex**(REAL n, STRING) | | 다음 평가에 사용될 일치(matched) 결과 배열의 위치를 설정한다. |
| **SetCaseMatch**(BOOLEAN) | | '...MATCH' 메소드들과 함께 사용되며, 매칭 시 대소문자 구분 여부를 정의한다. |
| **Initialise**() | | next 카운터를 초기화한다. |
| **EvaluateTable**() | | 테이블의 기본 키(primary key)에 대해 재평가하고 다시 정렬한다. |
| **Keys**() | STRING ARRAY | 이 리포트에서 사용된 컬럼 키(key)들인 STRING 배열을 반환한다. |
| **ColumnFormat**(STRING key) | COLUMNFORMAT | 전달된 컬럼 키의 컬럼 포맷을 반환한다. |
| **ColumnHeading**(STRING key) | [[STRING\|STRING Object]] | 키로 식별되는 컬럼의 헤딩을 반환한다. |
| **Table**() | TABLE | 이 리포트에서 사용된 테이블을 반환한다. |
| **CaseMatch**() | [[BOOLEAN\|BOOLEAN Object]] | MATCH STRING이 대소문자를 구분하는지 조회한다. SetCaseMatch(BOOLEAN)을 사용하여 설정한다. |
| **Results**(ARRAY Dtext, ARRAY Rtext) | [[BOOLEAN\|BOOLEAN Object]] | 테이블의 모든 항목(entries)을 사용하여 리포트를 평가한다 (항목당 1줄 이상일 수 있다. 컬럼 포맷이 줄 바꿈(wrap-around)을 유발하는 경우 Rtext가 반복된다). 평가할 항목이 있으면 TRUE, 없으면 FALSE를 반환한다. Rtext와 Dtext 모두 존재해야 하며, 값들로 업데이트된다. |
| **Results**(ARRAY) | [[BOOLEAN\|BOOLEAN Object]] | 위와 같으나 Dtext만 평가된다. |
| **ResultsMatch**(STRING, ARRAY, ARRAY) | [[BOOLEAN\|BOOLEAN Object]] | Results()와 유사하나 문자열과 일치하는 값만 두 배열에 들어간다. |
| **ResultsMatch**(STRING, ARRAY) | [[BOOLEAN\|BOOLEAN Object]] | 위와 같으나 Dtext만 평가된다. |
| **NextEntries**(REAL n, ARRAY Dtext, ARRAY Rtext) | [[BOOLEAN\|BOOLEAN Object]] | 테이블의 다음 n개 항목을 사용하여 리포트를 평가한다 (항목당 1줄 이상일 수 있으며, 컬럼 포맷이 줄 바꿈을 유발하면 Rtext가 반복된다). 평가할 항목이 있으면 TRUE, 없으면 FALSE를 반환한다. Rtext와 Dtext 모두 존재해야 하며, 다음 n개 값들로 업데이트된다. |
| **NextEntries**(REAL n, ARRAY) | [[BOOLEAN\|BOOLEAN Object]] | 위와 같으나 Dtext만 평가된다. |
| **NextLines**(REAL n, ARRAY Dtext, ARRAY Rtext) | [[BOOLEAN\|BOOLEAN Object]] | 테이블의 다음 n개 라인(lines)으로 리포트를 평가한다. 컬럼 포맷이 줄 바꿈을 유발하면 Rtext가 반복된다. 반환값은 평가할 라인이 있는지 나타내는 BOOLEAN이다. Rtext와 Dtext 모두 존재해야 하며, 다음 n개 값들로 업데이트된다. |
| **NextLines**(REAL n, ARRAY) | [[BOOLEAN\|BOOLEAN Object]] | 위와 같으나 Dtext만 평가된다. |
| **NextEntriesMatch**(REAL n, STRING value, ARRAY Dtext, ARRAY Rtext) | [[BOOLEAN\|BOOLEAN Object]] | NextEntries()와 유사하나 value와 일치하는 값만 두 배열에 들어간다. |
| **NextEntriesMatch**(REAL n, STRING value, ARRAY Dtext) | [[BOOLEAN\|BOOLEAN Object]] | 위와 같으나 Dtext만 평가된다. |
| **NextEntriesIndex**() | [[REAL\|REAL Object]] | 항목(entries) 배열에서의 현재 위치를 반환한다. |
| **NextLinesIndex**() | [[REAL\|REAL Object]] | 항목(entries) 배열에서의 현재 위치를 반환한다. |
| **NextEntriesIndex**(STRING) | [[REAL\|REAL Object]] | 일치된 값(matched values) 배열의 현재 카운트를 반환한다. STRING은 키워드 'MATCH'이다. |