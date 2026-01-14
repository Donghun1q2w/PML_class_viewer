---
tags: [PML2, E3D, Gadget, Form, UI]
aliases: [TOGGLE Object]
classification: Forms and Menu Objects & Gadgets
---

# [[TOGGLE]]

## 개요
TOGGLE 명령은 토글 가젯을 정의하며 위치, 태그 및 콜백 텍스트를 지정합니다. 또한 기본 ON 및 OFF 상태에 대해 다른 텍스트 문자열을 지정할 수 있습니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Val** | [[BOOLEAN\|BOOLEAN Object]] | TRUE와 FALSE 사이의 값을 토글합니다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **AddPixmap** (STRING file1, STRING file2, STRING file3) | NO RESULT | 선택되지 않은 상태(unselected), 선택된 상태(selected), 비활성 상태(inactive)에 사용될 픽스맵을 추가합니다. 마지막 두 인자는 선택 사항입니다. |
| **FullName** () | [[STRING\|STRING Object]] | 전체 가젯 이름(예: '!!Form.gadget')을 가져옵니다. |
| **Name** () | [[STRING\|STRING Object]] | 가젯의 이름(예: 'gadget')을 가져옵니다. |
| **Owner** () | FORM | 소유하고 있는 폼(form)을 가져옵니다. |
| **SetFocus** () | NO RESULT | 키보드 포커스를 이 가젯으로 이동합니다. |
| **SetPopup** (MENU menu) | NO RESULT | 지정된 메뉴를 팝업으로 가젯과 연결합니다. |
| **RemovePopup** (MENU menu) | NO RESULT | 가젯에서 지정된 팝업 메뉴를 제거합니다. |
| **GetPickedPopup** () | MENU | 가젯에 대해 마지막으로 선택된 팝업 메뉴를 반환합니다. |
| **Refresh** () | NO RESULT | 가젯의 표시(display)를 새로 고칩니다. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | '보여짐(shown)' 상태를 가져옵니다. |
| **SetToolTip** (STRING text) | [[STRING\|STRING Object]] | 툴팁(TOOLTIP)의 텍스트를 설정하거나 편집합니다. |
| **Type** () | [[STRING\|STRING Object]] | 가젯 유형을 문자열로 가져옵니다. |
| **Background** () | [[STRING\|STRING Object]] | 배경 색상 이름(Background Colour Name)을 가져옵니다. \u003cbr\u003e일부 가젯(예: 픽스맵을 표시하는 가젯)은 모든 상황에서 이 속성을 지원하지 않습니다. 색상이 명시적으로 설정되지 않은 가젯은 알려진 색상 이름을 갖지 않을 수 있으며, 이 경우 오류가 발생합니다. |

## 커맨드 (Commands)

```pml
\u003e-- TOGGLE gname -+- \u003cfgtagw\u003e -----------|
                  +- PIXMAP \u003cvshap\u003e -----|
                  +- CALLback text ------|
                  +- \u003cfgpos\u003e ------------|
                  +- \u003cfganch\u003e -----------|
                  +- \u003cfgdock\u003e -----------|
                  +- TOOLTIP text -------|
                  +- CORE ---------------* Core managed gadget
                  |
                  +- STATES text1 text2 -.
                  ‘----------------------+- TOOLTIP text -.
                                         ‘----------------‘---\u003e
```
*여기서 `text1`은 OFF 설정에 해당하고 `text2`는 ON 설정에 해당합니다.*

```pml
AddPixmap( !pixmap1 is STRING )
AddPixmap( !pixmap1 is STRING, !pixmap2 is STRING )
```
*여기서 `!pixmap`은 필요한 .png 파일의 경로 이름을 담고 있는 문자열입니다 (예: `%pmllib%\png\camera.png`). `!pixmap1`은 가젯의 선택되지 않은(Un-selected) 상태를 보여주고, `!pixmap2`는 선택된(Selected) 상태를 보여줍니다.*

## 노트 (Notes)
- 가젯을 다른 가젯 위에 배치하는 것은 좋지 않은 관행입니다. 이는 가젯이 가려지는 결과를 초래할 수 있습니다.
- 토글 설정에 대한 기본 텍스트 문자열은 'OFF'와 'ON'입니다. 토글이 처음 정의될 때의 기본 상태는 'OFF'(버튼이 올라간 상태)입니다.
- 가젯을 정의할 때 나중에 추가할 가장 큰 픽스맵을 포함할 수 있도록 크기를 설정하는 것이 권장됩니다. 이를 수행하지 않으면 예상치 못한 동작이 발생할 수 있습니다.
- 역사적으로 가젯이 비활성화되었을 때 사용되는 세 번째 픽스맵을 추가할 수 있었습니다. 픽스맵된 가젯은 비활성화 시 자동으로 회색 처리되므로(greyed-out) 이 관행은 더 이상 필요하지 않습니다.