---
tags: [PML2, E3D, GraphicalSelection, SelectionSet]
aliases: [Graphical Selection Object, SELECTION Object]
classification: PDMS Objects
---

# [[SELECTION]]

## 개요
Selection 오브젝트는 PML 사용자가 그래픽 선택 세트(graphical selections set)와 상호 작용할 수 있게 한다. 이 오브젝트는 PDMS가 그래픽 모드에 있을 필요가 없으며, TTY 모드에서도 선택 세트를 생성하고 조작할 수 있어 회귀 테스트 등에 사용할 수 있다. 유의미한(significant) 요소만 선택 세트에 포함될 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **selection** () | SELECTION | 빈 selection 오브젝트를 생성한다. |
| **scope** (DBREF) | [[BOOLEAN\|BOOLEAN Object]] | 선택의 범위(scope)를 정의한다. 즉, 선택된 요소가 존재해야 하는 최상위 요소를 정의하며, 기본값은 WORLD이다. |
| **add** (DBREF) | [[dbref\|dbref Object]] | 전달된 요소의 가장 상위 유의미한 부모(highest significant parent)를 선택에 추가한다. |
| **addConnected** (DBREF) | [[ARRAY\|ARRAY Object]] | 배관 구성요소에 대해 "Select connected"를 시뮬레이션한다. 주어진 구성요소와 그에 상대적인 연결된 네트워크를 추가한다. |
| **addBranchLeg** (DBREF) | [[ARRAY\|ARRAY Object]] | 배관 구성요소에 대해 "Select leg"를 시뮬레이션한다. 주어진 구성요소와 전달된 구성요소와 동일한 leg 내에 있는 분기(branch) 내 인접 구성요소를 추가한다. |
| **addAttached** (DBREF) | [[ARRAY\|ARRAY Object]] | 섹션(section)에 대해 "Select attached"를 시뮬레이션한다. 주어진 섹션과 선택에 부착된 모든 섹션을 추가한다. |
| **addOffspring** (DBREF) | [[ARRAY\|ARRAY Object]] | 주어진 요소의 가장 상위 유의미한 하위 요소들을 선택에 추가한다. 이 작업은 DBREF가 선택의 조상(ancestor)인 것처럼 수행된다. |
| **remove** (DBREF) | No Result | 전달된 요소의 가장 상위 유의미한 부모를 선택에서 제거한다. |
| **clear** () | No Result | 선택을 비운다. |
| **getCurrent** () | No Result | selection 오브젝트의 내용을 현재 그래픽 선택 세트의 내용으로 설정한다. |
| **getAll** () | No Result | 선택 세트가 전체 그리기 목록(drawlist)을 포함하도록 설정한다. |
| **setCurrent** () | No Result | 현재 그래픽 선택 세트를 selection 오브젝트의 내용과 동일하게 설정한다. |
| **isValid** () | [[BOOLEAN\|BOOLEAN Object]] | 선택이 유효한지 확인한다. (이는 표준 메소드이며 일반적으로 호출할 필요가 없다.) |
| **selected** (DBREF) | [[dbref\|dbref Object]] | 주어진 요소의 가장 상위 유의미한 부모, 즉 선택에 포함될 요소를 반환한다. |
| **isSelectable** (DBREF) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 요소가 선택 범위 내에서 그 자체로 선택 가능한 경우 true를 반환한다. |
| **isModifiable** (DBREF) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 요소의 가장 상위 유의미한 부모가 수정 가능한 경우 true를 반환한다. |
| **inSelection** (DBREF) | [[BOOLEAN\|BOOLEAN Object]] | 주어진 요소가 선택에 존재하는 경우 true를 반환한다. |
| **ancestors** (DBREF) | ARRAY of DBREFs | 현재 범위 내에서 주어진 요소에 대해 허용 가능한 조상 목록을 반환한다. |
| **getSelection** () | ARRAY of DBREFs | 선택에 포함된 모든 요소를 반환한다. |

## 노트 (Notes)
- 유의미한 요소(significant elements)만이 선택 세트에 포함될 수 있다. 무엇이 유의미한지에 대한 정의는 그래픽 상호 작용 모드에 따라 다르다:
    - Design 탐색 모드(Design navigate mode)에서는 모든 데이터베이스 요소가 유의미하다.
    - Model Editor 모드에서는 Model Editor 정의에 정의된 데이터베이스 요소와 일부 비-데이터베이스 요소만 유의미하다.
    - Draft 모드에서는 그리기 목록(drawlist) 요소만 유의미하다.
- 대부분의 메소드는 '가장 상위 유의미한 요소(highest significant element)'를 찾는다. 즉, 'scope' 값에 도달할 때까지 소유권 트리를 올라가며 유의미한 요소를 찾고, 이 천장(ceiling) 아래에 있는 가장 가까운 유의미한 요소를 사용한다.
- 이 오브젝트는 그래픽 선택 세트 자체를 조작한다. 요소가 추가되거나 제거됨에 따라, 그래픽 뷰에서도 동시에 강조 표시된다(그래픽 모드인 경우).