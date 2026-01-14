---
tags: [PML2, E3D, Expression, Evaluation]
aliases: [BLOCK Object]
classification: PML Built-in Objects
---

# [[BLOCK]]

## 개요
이 객체는 나중에 평가되는 표현식을 보관한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Block** (STRING expression) | BLOCK | 블록 표현식을 생성한다. |
| **Evaluate** () | ANY | 객체에 대한 블록 표현식을 평가한다: 결과가 TYPE 타입인지 확인한다. |
| **Evaluate** () | ANY | 표현식을 평가하고 결과를 반환한다. |
| **Evaluate** (STRING type) | ANY | 표현식을 평가하고 결과가 TYPE 타입이 아니면 오류를 반환한다. 그렇지 않으면 결과를 반환한다. |