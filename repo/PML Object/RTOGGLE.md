---
tags: [PML2, E3D, Forms, Gadgets, RadioButton]
aliases: [RTOGGLE Object]
classification: Forms and Menu Objects & Gadgets
---

# [[RTOGGLE]]

## 개요
RTOGGLE 가젯(TOGGLE 가젯과 매우 유사함)은 FRAMES 내에서만 허용된다. FRAME에 추가할 수 있으며, 추가되는 순서대로 1, 2, 3…으로 암묵적으로 번호가 매겨진다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **val** | [[BOOLEAN\|BOOLEAN Object]] | 현재 값 true 또는 false. |
| **index** | [[REAL\|REAL Object]] | 그룹 내 라디오 버튼의 인덱스. (Get Only) |
| **onVal** | [[STRING\|STRING Object]] | 연관된 선택된(selected) 값. |
| **offVal** | [[STRING\|STRING Object]] | 연관된 선택되지 않은(unselected) 값. |
| **visible** | [[BOOLEAN\|BOOLEAN Object]] | 가시성(Visibility). |
| **active** | [[BOOLEAN\|BOOLEAN Object]] | 활성화(회색 처리) 상태. |
| **callback** | [[STRING\|STRING Object]] | 콜백 문자열. |
| **tag** | [[STRING\|STRING Object]] | 태그 텍스트. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **FullName** ( ) | [[STRING\|STRING Object]] | 전체 가젯 이름을 가져온다 (예: '!!Form.gadget'). |
| **Name** ( ) | [[STRING\|STRING Object]] | 가젯의 이름을 가져온다 (예: 'gadget'). |
| **Owner** ( ) | FORM | 소유하고 있는 폼(form)을 가져온다. |
| **SetPopup** ( MENU ) | NO RESULT | 주어진 메뉴를 팝업으로 가젯과 연결한다. |
| **RemovePopup** ( MENU ) | NO RESULT | 가젯에서 주어진 팝업 메뉴를 제거한다. |
| **GetPickedPopup** ( ) | MENU | 가젯에 대해 마지막으로 선택된 팝업 메뉴를 반환한다. |
| **Refresh** ( ) | NO RESULT | 가젯의 표시를 새로 고친다. |
| **Shown** ( ) | [[BOOLEAN\|BOOLEAN Object]] | 'shown' 상태를 가져온다. |
| **SetToolTip** ( STRING ) | NO RESULT | 툴팁의 텍스트를 설정하거나 편집한다. |
| **Type** ( ) | [[STRING\|STRING Object]] | 가젯 타입을 문자열로 가져온다. |
| **Background** ( ) | [[STRING\|STRING Object]] | 배경 색상 이름을 가져온다. 일부 가젯은 모든 상황(예: 픽스맵이 표시되는 경우)에서 이 속성을 지원하지 않으며, 색상이 명시적으로 설정되지 않은 경우 알려진 색상 이름을 가지지 않을 수 있어 오류가 발생할 수 있다. |

## 커맨드 (Commands)

```text
.-------\u003c------------.
/ |
\u003e- RTOGgle gname -+- tagtext ------------|
+- CALLback text —-----|
+- \u003cfgpos\u003e ------------|
+- \u003cfganch\u003e -----------|
+- \u003cfgdock\u003e -----------|
+- TOOLTIP text -------|
+- CORE ---------------* Core managed gadget
|
+- STATES offval onval .
‘----------------------+- TOOLTIP text -.
‘----------------‘---\u003e
```

## 노트 (Notes)
- offval과 onval은 라디오 버튼 상태인 선택 해제(unselected) 또는 선택(selected)과 연관된 문자열 값이다. 기본값은 onval = ‘ON’, offval = ‘OFF’이다.
- 라디오 그룹 Frame 가젯에 의한 (이제 제거된) RADIO 가젯 사용을 대체하는 작업을 단순화하기 위해, RTOGGLE 가젯의 UNSELECT 이벤트는 PML open callback이 정의된 경우에만 발생한다. 이를 통해 콜백을 수정할 필요 없이 TOGGLE 가젯을 RTOGGLE 가젯으로 간단하게 대체할 수 있다.