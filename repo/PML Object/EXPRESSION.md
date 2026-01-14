---
tags: [PML2, E3D, Collection Filter, Database Element, Collection and Report Objects]
aliases: [EXPRESSION Object]
classification: Collection and Report Objects
---

# [[EXPRESSION]]

## 개요
이 Object는 데이터베이스 요소나 다른 Object에 적용하여 BOOLEAN, STRING 등 데이터 유형의 결과를 반환하는 기본 표현식을 정의하는 데 사용된다. EXPRESSION Object는 COLLECTION Object에서 수집 결과를 필터링하는 데 사용될 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Expression** |  | 생성자 (Object의 모든 설정을 초기화한다). |
| **Expression** (STRING) |  | 표현식을 구성하고 정의한다. 속성에는 속도와 효율성을 위해 ('ATTRIBUTE----') 형식을 사용해야 한다. 다른 예시로는 ('PURP eq IPIPINGI') 또는 ('XLEN + STRING(XLEN)')이 있다. |
| **AttributeExpression** (STRING) |  | 전달된 속성을 표현식으로 만든다. `AttributeExpression ('LENGTH')`는 `Expression ('ATTRIBUTE LENGTH')`와 동일하다. |
| **String**() | [[STRING\|STRING Object]] | 현재 표현식을 문자열로 반환한다. |
| **Evaluate** (DBREF) | ANY | 전달된 Object에 대해 현재 표현식을 평가한다. |