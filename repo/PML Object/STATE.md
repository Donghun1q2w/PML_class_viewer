---
tags: [PML2, E3D, Design, ModifyMode]
aliases: [STATE Object]
classification: PDMS Objects
---

# [[STATE]]

## 개요
STATE 오브젝트는 수정 모드(modify mode)의 상태를 조회하고 수정하기 위한 인터페이스를 제공한다. 이는 그래픽 모드에서 실행 중인 Design 모듈에서만 사용할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **state** () | constructor | 생성자 |
| **modifyMode** () | [[BOOLEAN\|BOOLEAN Object]] | 수정 모드가 켜져 있으면 TRUE를 반환하고, 그렇지 않으면 FALSE를 반환한다. |
| **modifyMode** (BOOLEAN) | none | 수정 모드를 켜거나 끈다. |
| **enableModifyMode** () | [[BOOLEAN\|BOOLEAN Object]] | 수정 모드가 활성화되어 있으면 TRUE를 반환하고, 그렇지 않으면 FALSE를 반환한다. |
| **enableModifyMode** (BOOLEAN) | [[BOOLEAN\|BOOLEAN Object]] | TRUE이면 수정 모드가 활성화된다. FALSE이면 수정 모드가 비활성화되지만, 이미 켜져 있는 경우에는 아무런 효과가 없다. 작업이 성공하면 TRUE를, 그렇지 않으면 FALSE를 반환한다. |
| **featureHighlight** (BOOLEAN) | No Result | TRUE이면 커서가 지나갈 때 기능(ppoints, plines, vertices 등)이 3D 뷰에서 일시적으로 강조 표시된다. 이를 FALSE로 설정하면 이 기능이 꺼진다. |