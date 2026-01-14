---
tags:
  - PML2
  - E3D
  - STRING
  - Text
  - Object
  - string
aliases:
  - STRING Object
classification: PML Built-in Objects
---

# [[STRING]]

## 개요

String.real()은 REAL(string)과 같은 방식으로 문자열을 숫자로 변환하며, 해석 가능한 확장된 피트 및 인치 형식 집합을 포함한다. 결과 실수는 문자열의 단위와 일치하는 현재 단위가 된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **After** (STRING two) | [[String\|String Object]] | 첫 번째 하위 문자열 `two`의 출현 이후의 하위 문자열을 반환한다. |
| **Before** (STRING two) | [[String\|String Object]] | 첫 번째 하위 문자열 `two`의 출현 이전의 하위 문자열을 반환한다. |
| **Block** () | BLOCK | STRING을 평가를 위한 BLOCK으로 만든다. |
| **Boolean** () | [[boolean\|boolean Object]] | STRING이 'TRUE', 'T', 'YES', 'Y'이면 TRUE, 'FALSE', 'F', 'NO', 'N'이면 FALSE이다. |
| **Bore** () | BORE | STRING을 BORE로 변환한다 (정확한 변환 - NEARESTBORE 참조). |
| **Bore** (FORMAT format) | BORE | 전역 FORMAT 객체의 설정을 사용하여 STRING을 BORE로 변환한다. |
| **DBRef** () | [[dbref\|dbref Object]] | STRING을 DBREF로 변환한다. |
| **DBRef** (FORMAT format) | [[dbref\|dbref Object]] | 전역 format 객체의 설정을 사용하여 STRING을 DBREF로 변환한다. |
| **Digits** () | [[Real\|Real Object]] | 문자열이 10진수 숫자만 포함하는 경우, 표현된 양수 값을 반환하고, 그렇지 않으면 -1.0을 반환한다. 이는 유니코드가 지원하는 모든 언어의 숫자 문자를 처리한다. |
| **Direction** () | [[Direction\|Direction Object]] | STRING을 DIRECTION으로 변환한다. |
| **Direction** (FORMAT format) | [[Direction\|Direction Object]] | 전역 format 객체의 설정을 사용하여 STRING을 DIRECTION으로 변환한다. |
| **Empty** () | [[boolean\|boolean Object]] | 길이가 0인 빈 문자열이면 TRUE를 반환한다. |
| **EQNoCase** (STRING) | [[boolean\|boolean Object]] | 대소문자를 무시하고 주어진 문자열과 비교하여 같으면 TRUE를 반환한다. |
| **isDigits** () | [[boolean\|boolean Object]] | 문자열이 10진수 숫자로만 구성된 연속된 문자열인지 확인한다. 이는 유니코드가 지원하는 모든 언어의 숫자 문자를 포함한다. |
| **isLetters** () | [[boolean\|boolean Object]] | 문자열이 문자로만 구성된 연속된 문자열인지 확인한다. 이는 유니코드가 지원하는 모든 언어의 문자 문자를 포함한다. |
| **isLettersAndDigits** () | [[boolean\|boolean Object]] | 문자열이 문자와 10진수 숫자로만 구성된 연속된 문자열인지 확인한다. 이는 유니코드가 지원하는 모든 언어의 문자와 숫자를 포함한다. |
| **Length** () | [[Real\|Real Object]] | 문자열의 문자 수를 반환한다. |
| **LowCase** () | [[String\|String Object]] | 문자열을 소문자로 변환한다. |
| **LT** (STRING) | [[boolean\|boolean Object]] | ASCII 조합(collating) 순서를 사용하여 비교한다. |
| **Match** (STRING two) | [[Real\|Real Object]] | 첫 번째 문자열 내에서 하위 문자열 `two`의 시작 위치를 반환한다. 찾지 못하면 0을 반환한다. |
| **MatchWild** (STRING two) | [[boolean\|boolean Object]] | 문자열이 같으면 TRUE를 반환한다. STRING `two`는 와일드카드 문자를 포함할 수 있다. `*`는 임의의 수의 문자, `?`는 단일 문자이다. |
| **MatchWild** (STRING two, STRING multiple) | [[boolean\|boolean Object]] | 위와 같으나 `multiple`이 임의의 수의 문자에 대한 와일드카드를 재정의한다. |
| **MatchWild** (STRING two, STRING multiple, STRING single) | [[boolean\|boolean Object]] | 위와 같으나 `multiple`과 `single`이 각각 와일드카드를 재정의한다. |
| **Occurs** (STRING) | [[Real\|Real Object]] | 주어진 문자열의 발생 횟수를 반환한다. |
| **Orientation** () | [[orientation\|orientation Object]] | STRING을 ORIENTATION으로 변환한다. |
| **Orientation** (FORMAT !!format) | [[orientation\|orientation Object]] | 전역 `!!format`을 사용하여 STRING을 ORIENTATION으로 변환한다. |
| **Part** (REAL nth) | [[String\|String Object]] | 공백, 탭 또는 개행으로 구분된 필드 중 `nth` 번째 필드를 추출한다. |
| **Part** (REAL nth, STRING delim) | [[String\|String Object]] | `delim`으로 구분된 필드 중 `nth` 번째 필드를 추출한다. |
| **Position** () | [[position\|position Object]] | STRING을 POSITION으로 변환한다. |
| **Position** (FORMAT !!format) | [[position\|position Object]] | 전역 `!!format` 객체의 설정을 사용하여 STRING을 POSITION으로 변환한다. |
| **REAL** () | [[Real\|Real Object]] | 숫자로 변환한다. |
| **Replace** (STRING two, STRING three) | [[String\|String Object]] | 하위 문자열 `two`의 모든 발생을 하위 문자열 `three`로 바꾼다. |
| **Replace** (STRING two, STRING three, REAL nth) | [[String\|String Object]] | `nth` 번째 발생(또는 끝에서 `-nth` 번째 발생)부터 시작하여 하위 문자열 `two`의 모든 발생을 `three`로 바꾼다. |
| **Replace** (STRING two, STRING three, REAL nth, REAL count) | [[String\|String Object]] | `nth` 번째 발생(또는 끝에서 `-nth` 번째 발생)부터 시작하여 하위 문자열 `two`의 `count`개 발생을 `three`로 바꾼다. |
| **Split** () | [[Array\|Array Object]] | 공백(다중 공백은 압축됨)에서 문자열을 분할하여 STRINGS의 ARRAY로 반환한다. |
| **Split** (STRING delim) | [[Array\|Array Object]] | `delim`(다중 `delim`은 압축되지 않음)에서 문자열을 분할하여 STRINGS의 ARRAY로 반환한다. |
| **String** (BLOCK) | [[String\|String Object]] | BLOCK 표현식에서 STRING을 생성한다. |
| **String** (BOOLEAN) | [[String\|String Object]] | TRUE 또는 FALSE와 같은 STRING을 생성한다. |
| **String** (BOOLEAN, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 BOOLEAN에서 STRING을 생성한다. |
| **String** (BORE) | [[String\|String Object]] | BORE에서 STRING을 생성한다. |
| **String** (BORE, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 BORE에서 STRING을 생성한다. |
| **String** (DB) | [[String\|String Object]] | DB 이름을 포함하는 STRING을 생성한다. |
| **String** (DB, FORMAT) | [[String\|String Object]] | DB 이름을 포함하는 STRING을 생성한다. (FORMAT 인수는 Forms 및 Menus와의 일관성을 위해 필요함). |
| **String** (DIRECTION) | [[String\|String Object]] | DIRECTION에서 STRING을 생성한다. |
| **String** (DIRECTION, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 DIRECTION에서 STRING을 생성한다. |
| **String** (FORMAT) | [[String\|String Object]] | 전역 FORMAT 객체의 설정을 사용하여 STRING을 STRING으로 변환한다. |
| **String** (MDB) | [[String\|String Object]] | MDB 이름을 포함하는 STRING을 생성한다. |
| **String** (ORIENTATION) | [[String\|String Object]] | ORIENTATION에서 STRING을 생성한다. |
| **String** (ORIENTATION, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 ORIENTATION에서 STRING을 생성한다. |
| **String** (POSITION) | [[String\|String Object]] | POSITION에서 STRING을 생성한다. |
| **String** (POSITION, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 POSITION에서 STRING을 생성한다. |
| **String** (PROJECT) | [[String\|String Object]] | PROJECT 코드를 포함하는 STRING을 생성한다. |
| **String** (REAL) | [[String\|String Object]] | REAL에서 STRING을 생성한다. |
| **String** (REAL, FORMAT) | [[String\|String Object]] | FORMAT 객체에 지정된 대로 REAL에서 STRING을 생성한다. |
| **String** (REAL, STRING) | [[String\|String Object]] | REAL에서 STRING을 생성한다. STRING 인수는 구식 형식 Dn으로 소수 자릿수를 변환하기 위해 존재한다. |
| **String** (SESSION) | [[String\|String Object]] | SESSION 번호를 포함하는 STRING을 생성한다. |
| **String** (TEAM) | [[String\|String Object]] | TEAM 이름을 포함하는 STRING을 생성한다. |
| **String** (USER) | [[String\|String Object]] | USER 이름을 포함하는 STRING을 생성한다. |
| **Substring** (REAL index, REAL nchars) | [[String\|String Object]] | `index`에서 시작하여 길이 `nchars`인 하위 문자열을 반환한다. |
| **Substring** (REAL index) | [[String\|String Object]] | `index`에서 문자열 끝까지의 하위 문자열을 반환한다. |
| **Trim** () | [[String\|String Object]] | 선행 및 후행 공백을 제거한다. |
| **Trim** (STRING options, STRING char) | [[String\|String Object]] | STRING 전체에서 `char`의 다중 발생을 단일 발생으로 줄인다 (`options = 'M'`). |
| **Trim** (STRING options) | [[String\|String Object]] | 선행 공백(`options='L'`), 후행 공백(`options='R'`) 또는 둘 다(`options='LR'`)를 제거한다. |
| **UpCase** () | [[String\|String Object]] | STRING을 대문자로 변환한다. |
| **VLogical** () | [[boolean\|boolean Object]] | STRING을 BOOLEAN으로 평가한다. |
| **VText** () | [[String\|String Object]] | STRING을 STRING으로 평가한다. |
| **VValue** () | [[Real\|Real Object]] | STRING을 REAL로 평가한다. |

## 노트 (Notes)

* **Compare Strings Ignoring Case**: `if( !this.attrib.eqNoCase('Name') )` 구조는 `if( !this.attrib.upcase() eq 'NAME' )` 형식의 비교보다 효율적이며, 특히 검사가 실패할 때 더욱 그렇다. 또한 비교 대상 값의 대소문자가 무엇이든 상관없으므로 더 안정적이다. 기존 Appware에서 이러한 검사를 다시 방문하여 새로운 구조로 교체하면 진단되지 않은 결함을 수정하고 성능을 향상시킬 수 있다.

* **Is String Letters Only?:
Example:
* **Is String Digits Only?
Example:'
* **Get Value Of Digits Only String
Example:
!val = !strdgts.Digits()
q var !val
<REAL> 1234

* **Is String Letters And Digits Only?:
Example:

```
aa = new aa()
```


```
`!strmix= !strlet + !strdgts
q var !strmix.isLettersAndDigits()
<BOOLEAN> TRUE
q var !strmix.isLetters()
<BOOLEAN> FALSE
q var !strmix.Digits()
<REAL> -1
q var !strlet.isLettersAndDigits()
<BOOLEAN> TRUE
q var !strdgts.isLettersAndDigits()
<BOOLEAN> TRUE`
```

