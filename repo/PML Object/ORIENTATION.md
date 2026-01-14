---
tags: [PML2, E3D, Geometry, PDMS]
aliases: [ORIENTATION Object]
classification: PDMS Objects
---

# [[ORIENTATION]]

## 개요
이 Object는 기준 데이터베이스 레퍼런스(origin database reference)에 의해 정의된 참조 프레임 내에서 참조 프레임의 오리엔테이션(즉, XYZ 축의 방향)을 정의한다. 이것은 위치(position)를 정의하지 않는다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Alpha** | [[REAL\|REAL Object]] | 알파 컴포넌트. |
| **Beta** | [[REAL\|REAL Object]] | 베타 컴포넌트. |
| **Gamma** | [[REAL\|REAL Object]] | 감마 컴포넌트. |
| **Origin** | [[dbref\|dbref Object]] | 원점(origin)인 DB 요소. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Orientation** ( STRING ) | [[orientation\|orientation Object]] | 주어진 값들로부터 ORIENTATION을 생성한다. |
| **Orientation** ( STRING, FORMAT ) | [[orientation\|orientation Object]] | 지정된 FORMAT으로 주어진 값들로부터 ORIENTATION을 생성한다. |
| **EQ** (ORIENTATION) | [[BOOLEAN\|BOOLEAN Object]] | ORIENTATION들이 동일하면 TRUE를 반환한다. |
| **LT** (ORIENTATION) | [[BOOLEAN\|BOOLEAN Object]] | ORIENTATION이 인자보다 작으면 TRUE를 반환한다. |
| **String** (FORMAT) | [[STRING\|STRING Object]] | ORIENTATION을 STRING으로 변환한다. |
| **WRT** (DBREF) | [[orientation\|orientation Object]] | 주어진 DB 요소에 대한 새로운 ORIENTATION으로 변환한다. |
| **XDir** () | [[Direction\|Direction Object]] | ORIENTATION의 X축 방향을 DIRECTION으로 반환한다. |
| **YDir** () | [[Direction\|Direction Object]] | ORIENTATION의 Y축 방향을 DIRECTION으로 반환한다. |
| **ZDir** () | [[Direction\|Direction Object]] | ORIENTATION의 Z축 방향을 DIRECTION으로 반환한다. |