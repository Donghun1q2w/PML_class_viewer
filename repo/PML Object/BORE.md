---
tags: [PML2, E3D, PDMS, BORE]
aliases: [BORE Object]
classification: PDMS Objects
---

# [[BORE]]

## 개요
BORE 객체는 배관 구경(Bore)을 나타내는 PDMS 객체이다. 주어진 값으로 BORE 객체를 생성하거나, 현재 BORE 단위 설정을 기반으로 비교 및 변환 작업을 수행하는 데 사용된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Size** | [[REAL\|REAL Object]] | BORE 크기 |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **BORE** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 값으로 BORE 객체를 생성하는 생성자. |
| **BORE** (STRING value) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 값으로 BORE 객체를 생성하는 생성자. |
| **BORE** (STRING value, FORMAT format) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 값과 format에 명시된 형식으로 BORE 객체를 생성하는 생성자. |
| **EQ** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 인자 값과 비교한다. |
| **GEQ** (BORE bore) | [[BOOLEAN\|BOOLEAN Object]] | 이 객체가 인자 bore보다 크거나 같으면 TRUE를 반환한다. |
| **GEQ** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 인자 값과 비교한다. |
| **GT** (BORE bore) | [[BOOLEAN\|BOOLEAN Object]] | BORE가 인자 BORE보다 크면 TRUE를 반환한다. |
| **GT** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 인자 값과 비교한다. |
| **LEQ** (BORE bore) | [[BOOLEAN\|BOOLEAN Object]] | 이 객체가 인자 bore보다 작거나 같으면 TRUE를 반환한다. |
| **LEQ** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 인자 값과 비교한다. |
| **LT** (BORE bore) | [[BOOLEAN\|BOOLEAN Object]] | 이 객체가 인자 bore보다 작으면 TRUE를 반환한다. |
| **LT** (REAL value) | [[BOOLEAN\|BOOLEAN Object]] | 현재 BORE 단위에 의존하여 인자 값과 비교한다. |
| **Real** () | [[REAL\|REAL Object]] | BORE를 REAL 값으로 변환한다. |
| **String** (FORMAT format) | [[STRING\|STRING Object]] | 전역 format 객체의 설정을 사용하여 BORE를 STRING으로 변환한다. |

## 노트 (Notes)
- 이 메소드들 중 어떤 것도 원본 객체를 수정하지 않는다.