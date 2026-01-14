---
tags: [PML2, E3D, PML_Built_in_Objects, Collection, Data Structure]
aliases: [ARRAY Object]
classification: PML Built-in Objects
---

# [[ARRAY]]

## 개요
ARRAY 객체는 PML Built-in Object로 분류된다. 이 객체는 배열 내의 요소들을 추가, 삭제, 검색, 정렬 및 조작하는 다양한 메서드를 제공한다.

## 메소드 (Methods)

| Name                                           | Result                      | Purpose                                                                                                           |
| :--------------------------------------------- | :-------------------------- | :---------------------------------------------------------------------------------------------------------------- |
| **Append** (ANY value)                         | NO RESULT                   | **value**를 배열의 끝에 새로운 요소로 추가한다.                                                                                   |
| **AppendArray** (ARRAY values)                 | NO RESULT                   | **array** 값들을 배열의 끝에 새로운 요소들로 추가한다.                                                                               |
| **Clear** ()                                   | NO RESULT                   | 모든 요소를 제거한다.                                                                                                      |
| **Compress** ()                                | NO RESULT                   | 정의되지 않은(undefined) 모든 요소를 제거하고 남은 요소들을 재색인(re-index)한다.                                                           |
| **DeleteFrom** (REAL index, REAL n)            | ARRAY                       | **index**에서 시작하여 **n**개의 요소를 정의되지 않음(undefined)으로 만든다. 남은 요소들은 재색인되지 않는다. 삭제된 요소들의 배열을 반환한다(원하지 않는 경우 할당할 필요 없음). |
| **DeleteFrom** (REAL index)                    | ARRAY                       | **index**부터 배열의 끝까지 요소들을 정의되지 않음(undefined)으로 만든다. 삭제된 요소들의 배열을 반환한다. 남은 요소들은 재색인되지 않는다.                          |
| **DeleteTo** (REAL index, REAL n)              | ARRAY                       | **index**까지 **n**개의 요소를 정의되지 않음(undefined)으로 만든다. 삭제된 요소들의 배열을 반환한다. 남은 요소들은 재색인되지 않는다.                           |
| **DeleteTo** (REAL index)                      | ARRAY                       | 시작부터 **index**까지의 요소들을 정의되지 않음(undefined)으로 만든다. 삭제된 요소들의 배열을 반환한다. 남은 요소들은 재색인되지 않는다.                            |
| **Difference** (ARRAY two)                     | ARRAY                       | 원본 배열에는 있지만 **array two**에는 없는 요소들의 배열을 반환한다. 중복은 한 번만 나타난다.                                                      |
| **Empty** ()                                   | [[BOOLEAN\|BOOLEAN Object]] | 배열이 비어 있으면 TRUE이다.                                                                                                |
| **Evaluate** (BLOCK command)                   | NEW ARRAY                   | 각 요소에서 **command** 내의 코드를 평가한다.                                                                                   |
| **Find** (ANY value)                           | NEW ARRAY                   | 원본 배열에서 **value**를 검색하고 발견된 인덱스 위치들의 배열을 반환한다.                                                                    |
| **FindFirst** (ANY value)                      | REAL                        | **value**가 처음 나타나는 인덱스를 반환한다. 찾지 못하면 UNSET을 반환한다.                                                                 |
| **First** ()                                   | ANY                         | 정의된 첫 번째 요소의 값을 반환한다.                                                                                             |
| **From** (REAL index, REAL n)                  | ARRAY                       | **index**에서 시작하는 **n**개 요소의 하위 배열(sub array)을 복사한다.                                                               |
| **From** (REAL index)                          | ARRAY                       | **index**에서 시작하여 배열 끝까지의 하위 배열을 복사한다.                                                                             |
| **GetIndexed** (REAL index)                    | ANY                         | ARRAY[index]를 구현한다 (이는 내부 메서드임).                                                                                  |
| **Indices** ()                                 | NEW ARRAY                   | 값을 가진 대상 배열의 인덱스들을 포함하는 배열을 반환한다.                                                                                 |
| **Insert** (REAL index, ANY value)             | NO RESULT                   | **index** 위치에 **value**를 새로운 요소로 삽입한다. 이후의 요소들은 재색인된다.                                                            |
| **InsertArray** (REAL index, ARRAY ANY values) | NO RESULT                   | **index** 위치를 시작으로 **values**를 새로운 요소들로 삽입한다. 이후의 요소들은 재색인된다.                                                     |
| **Intersect** (ARRAY two)                      | NEW ARRAY                   | 두 배열 모두에 존재하는 요소들의 배열을 반환한다. 중복은 한 번만 나타난다.                                                                       |
| **Invert** ()                                  | NEW ARRAY                   | 배열의 역순 복사본을 반환한다.                                                                                                 |
| **Last** ()                                    | ANY                         | 마지막 요소의 값을 반환한다.                                                                                                  |
| **MaxIndex** ()                                | [[REAL\|REAL Object]]       | 정의된(비어 있지 않은) 마지막 요소의 첨자(Subscript)이다.                                                                            |
| **MinIndex** ()                                | [[REAL\|REAL Object]]       | 정의된(비어 있지 않은) 첫 번째 요소의 첨자이다.                                                                                      |
| **Overlay** (REAL index, ARRAY two)            | NEW ARRAY                   | **index** 위치의 배열 요소들을 **array two**의 요소들로 교체한다. 덮어씌워진 요소들의 배열을 반환한다(필요하지 않은 경우 할당할 필요 없음).                        |
| **ReIndex** (REAL ARRAY indices)               | NO RESULT                   | SORTEDINDICES의 결과를 적용하여 배열 요소들을 **indices**에 지정된 위치로 재정렬한다.                                                       |
| **Remove** (REAL nth)                          | ANY                         | **nth** 요소를 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                                       |
| **RemoveFirst** ()                             | ANY                         | 첫 번째 요소를 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                                          |
| **RemoveFrom** (REAL index, REAL n)            | NEW ARRAY                   | **index**로 시작하는 **n**개 요소의 새 배열을 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                  |
| **RemoveFrom** (REAL index)                    | NEW ARRAY                   | **index**부터 배열 끝까지의 요소들로 구성된 새 배열을 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                |
| **RemoveLast** ()                              | ANY                         | 마지막 요소를 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                                           |
| **RemoveTo** (REAL index, REAL n)              | NEW ARRAY                   | 시작부터 **index**까지 **n**개의 요소를 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                      |
| **RemoveTo** (REAL index)                      | NEW ARRAY                   | 시작부터 **index**까지의 요소들을 제거하고 반환한다(필요하지 않은 경우 할당할 필요 없음). 남은 요소들은 재색인된다.                                            |
| **Size** ()                                    | REAL                        | 정의된 요소의 수를 반환한다.                                                                                                  |
| **Sort** ()                                    | NO RESULT                   | 배열을 오름차순으로 정렬한다.                                                                                                  |
| **SortUnique** ()                              | NEW ARRAY                   | 중복이 제거되고 정렬된 배열의 복사본을 반환한다.                                                                                       |
| **SortedIndices** ()                           | NEW REAL ARRAY              | 배열 내 요소들의 정렬된 순서를 나타내는 새로운 인덱스 배열을 반환한다. 배열 자체는 정렬되지 않는다.                                                         |
| **To** (REAL index, REAL n)                    | ARRAY                       | 시작부터 **index**까지의 **n**개 요소 하위 배열을 복사한다.                                                                          |
| **To** (REAL index)                            | ARRAY                       | 배열의 시작부터 **index**까지의 하위 배열을 복사한다.                                                                                |
| **Union** (ARRAY two)                          | NEW ARRAY                   | 두 배열 중 하나라도 존재하는 요소들의 배열을 반환한다(중복은 한 번만 나타남).                                                                     |
| **Unique** ()                                  | NO RESULT                   | 중복을 제거하고 남은 요소들을 재색인한다.                                                                                           |
| **Width** ()                                   | REAL                        | 문자열 요소들의 최대 너비를 반환한다(다른 요소 유형은 무시됨).                                                                              |
