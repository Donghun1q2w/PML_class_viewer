---
tags: [PML2, E3D, Gadget, UI, Form, Selection]
aliases: [LIST Object]
classification: Forms and Menu Objects & Gadgets
---

# [[LIST]]

## 개요
LIST 명령은 단일 선택 또는 다중 선택 리스트 가젯을 정의하며, 그 위치, 태그, 컬럼 수 및 콜백 텍스트를 지정합니다. 또한 리스트의 표시되는 부분이 나타날 영역(너비 및 높이)을 정의합니다. 리스트 옵션에 대한 표시 텍스트(display texts)와 대체 텍스트(replacement texts)를 정의하는 배열은 일반적으로 폼의 기본 생성자(default constructor) 메소드에서 설정됩니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Val** | [[REAL\|REAL Object]] | 단일 선택(single-choice) 목록의 선택된 필드 번호입니다. |
| **Val** | REAL ARRAY | 다중 선택(multiple-choice) 목록의 선택된 필드 번호들입니다. |
| **DText** | STRING ARRAY | 전체 표시 텍스트(display texts) 목록을 설정하거나 가져옵니다. |
| **DText[n]** | [[STRING\|STRING Object]] | n번째 필드의 표시 텍스트를 가져옵니다. (Get Only) |
| **PickedField** | [[REAL\|REAL Object]] | 마지막으로 선택된(picked) 리스트 필드 번호입니다. (Get Only) |
| **RText** | STRING ARRAY | 대체 텍스트(replacement texts) 목록을 설정하거나 가져옵니다. |
| **RText[n]** | [[STRING\|STRING Object]] | n번째 필드의 대체 텍스트를 가져옵니다. (Get Only) |
| **Count** | [[REAL\|REAL Object]] | 리스트에 있는 필드의 수를 가져옵니다. (Get only) |
| **val** | [[REAL\|REAL Object]] | 정수 형태의 선택된 필드입니다. 0은 선택된 것이 없음을 의미합니다. 필수 선택(mandatory selection) 리스트에 대해 val을 0으로 설정하면 오류가 발생합니다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Add** (STRING Dtext) | NO RESULT | 리스트에 항목을 추가합니다. 여기서 Dtext는 옵션 목록에 표시할 텍스트입니다. |
| **Add** (STRING Dtext, STRING Rtext) | NO RESULT | 리스트에 항목을 추가합니다. 여기서 Dtext는 옵션 목록에 표시할 텍스트이고, Rtext는 새 필드에 대한 대체 텍스트입니다. Rtext가 지정되지 않으면 기본적으로 Dtext로 설정됩니다. |
| **FullName** () | [[STRING\|STRING Object]] | 가젯의 전체 이름(예: '!!Form.gadget')을 가져옵니다. |
| **Name** () | [[STRING\|STRING Object]] | 가젯의 이름(예: 'gadget')을 가져옵니다. |
| **Owner** () | FORM | 소유하고 있는 폼(owning form)을 가져옵니다. |
| **Select** (STRING text, STRING value) | NO RESULT | 리스트에서 지정된 항목을 선택합니다. text는 'Rtext' 또는 'Dtext'여야 하며, value는 선택될 항목의 RTEXT 또는 DTEXT입니다. |
| **Select** (STRING text, ARRAY of STRING values) | NO RESULT | 다중 선택 리스트 항목들을 선택합니다. text는 'Rtext' 또는 'Dtext'여야 합니다. values는 선택될 RTEXT 또는 DTEXT 값들을 포함합니다. |
| **Selection** ( ) | STRING ARRAY OF STRING | 선택된 RTEXT를 가져옵니다. 다중 선택 리스트의 경우 RTEXT 배열을 반환합니다. |
| **Selection** (STRING text) | STRING ARRAY OF STRING | 현재 선택항목의 RTEXT 또는 DTEXT를 가져옵니다. text는 'Rtext' 또는 'Dtext'여야 합니다. 다중 선택 리스트의 경우 텍스트 배열을 반환합니다. |
| **Clear** () | NO RESULT | 리스트 내용과 선택 항목들을 지웁니다. |
| **ClearSelection** () | NO RESULT | 리스트 선택 항목들만 지웁니다. |
| **SetPopup** (MENU menu) | NO RESULT | 메뉴를 팝업으로 가젯과 연결합니다. |
| **RemovePopup** (MENU menu) | NO RESULT | 가젯에서 팝업 메뉴를 제거합니다. |
| **GetPickedPopup** () | MENU | 가젯에 대해 마지막으로 선택된(picked) 팝업 메뉴를 반환합니다. |
| **Refresh** () | NO RESULT | 가젯의 표시(display)를 새로 고칩니다. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | '보임(shown)' 상태를 가져옵니다. |
| **Type** () | [[STRING\|STRING Object]] | 가젯 타입을 STRING으로 가져옵니다. |
| **SetToolTip** (STRING) | NO RESULT | TOOLTIP을 편집할 수 있게 합니다. |
| **SetFocus** () | NO RESULT | 키보드 포커스를 이 가젯으로 이동합니다. |
| **SetHeadings** (!Dtexts is STRING) | NONE | 열(column)의 수를 지정하고 리스트의 열 제목(headings)을 설정합니다. Dtexts는 탭(TAB)으로 구분된 하위 문자열 집합을 포함합니다. |
| **SetHeadings** (!Dtexts is ARRAY) | NONE | 열(column)의 수를 지정하고 리스트의 열 제목(headings)을 설정합니다. Dtexts는 문자열 배열입니다. |
| **Clear** (!dtext) | NO RESULT | 주어진 DTEXT 문자열을 가진 필드를 삭제합니다. |
| **Clear** (!fieldNumber) | NO RESULT | 지정된 필드 번호를 삭제합니다. |
| **SetRows** (Array of (Array of STRING)) | NO RESULT | 행(row) 단위로 리스트 가젯의 모든 데이터 필드에 대한 표시 텍스트를 설정합니다. 리스트 가젯이 이미 채워져 있는 경우 현재의 모든 행을 새 행으로 대체합니다. Array는 '행 배열(row arrays)'의 배열이며, 그 크기가 리스트의 행 수를 결정합니다. 각 항목은 문자열의 행 배열이며, 행의 각 열에 표시될 텍스트를 제공합니다. 각 행 배열의 크기는 리스트의 열 수보다 작거나 같아야 합니다. 열은 배열이 소진될 때까지 순차적으로 채워집니다. |
| **SetColumns** (Array of (Array of STRING)) | NO RESULT | 열(column) 단위로 리스트 가젯의 모든 데이터 필드에 대한 표시 텍스트를 설정합니다. 리스트 가젯이 이미 채워져 있는 경우 현재의 모든 행을 새 행으로 대체합니다. Array는 '열 배열(column arrays)'의 배열이며, 그 크기는 리스트의 열 수와 일치해야 합니다. 각 열 배열의 크기는 모두 동일해야 하며, 이는 리스트의 행 수를 결정합니다. |
| **Select** (REAL column, STRING dtext) | NO RESULT | 해당 열(column)이 표시 텍스트(dtext)를 가지고 있는 첫 번째 리스트 행을 선택합니다. 필드를 찾지 못하면 리스트 선택은 변경되지 않습니다. 다중 선택 리스트인 경우 이 메소드를 반복해서 사용하면 리스트에 선택 항목이 추가됩니다. |
| **Background** () | [[STRING\|STRING Object]] | 배경 색상 이름(Background Colour Name)을 가져옵니다. 픽스맵(pixmap)을 표시하는 가젯과 같이 일부 상황에서는 이 속성을 지원하지 않는 가젯도 있습니다. 색상이 명시적으로 설정되지 않은 가젯은 알려진 색상 이름을 가지지 않을 수 있으며, 이 경우 오류가 발생합니다. |

## 커맨드 (Commands)

```
\u003e-- \u003cflist\u003e - LIST gname -+- \u003cfgtagw\u003e ------|
                          +- \u003cfgpos\u003e -------|
                          +- \u003cfganch\u003e ------|
                          +- \u003cfgdock\u003e ------|
                          +- CALLback text -|
                          +- TOOLTIP text --|
                          +- CORE ----------* Core managed gadget
                          |
                          +- MULTiple --------.
                          |                   |
                          |  .-------\u003c-------.|
                          | /                ||
                          +- NORESELect ----||
                          +- ZEROSELection -*|
                          ‘-------------------‘- \u003cvshap\u003e +- TOOLTIP text -.
                                                         ‘----------------‘-\u003e
```

## 노트 (Notes)
1. UNSELECT 이벤트는 오픈 콜백(open callback)이 지정되지 않는 한 PML에 통지되지 않습니다 (SELECT와 UNSELECT 이벤트를 구별할 수 있도록 하기 위함).
2. 일반적으로 UNSELECT 액션은 Appware가 종속된 가젯이나 폼에 대한 선택 해제의 결과를 관리할 수 있도록 합니다.
3. UNSELECT 이벤트 내에서 프로그래밍 방식으로 리스트의 선택을 변경하지 않는 것을 권장합니다.
4. TOOLTIP 키워드는 문법의 두 가지 다른 위치에서 주어질 수 있습니다.