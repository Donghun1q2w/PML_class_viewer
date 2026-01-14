---
tags: [PML2, E3D, Gadget, GUI]
aliases: [BUTTON Object]
classification: Forms and Menu Objects & Gadgets
---

# [[BUTTON]]

## 개요
BUTTON 명령은 버튼을 정의하며 위치, 태그 또는 픽스맵, 콜백 텍스트 및 제어 속성을 지정한다. 버튼은 PML 제어 또는 코어 코드 제어로 정의할 수 있으며, 텍스트 전용 버튼 표현을 제공하는 Linklabel 유형도 있다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Background** | [[REAL\|REAL Object]] | 배경 색상 번호를 설정하거나 가져온다. (Set/Get) |
| **Background** | [[STRING\|STRING Object]] | 배경 색상 이름을 설정한다. (Set Only) |
| **Val** | [[BOOLEAN\|BOOLEAN Object]] | 버튼이 눌려있을 때 TRUE, 그렇지 않을 때 FALSE이다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **AddPixmap** (STRING file1, STRING file2, STRING file3) \u003cbr\u003e **AddPixmap** (STRING file1, STRING file2) \u003cbr\u003e **AddPixmap** (STRING file) | NO RESULT | 선택되지 않은 상태, 선택된 상태, 비활성 상태에 사용될 픽스맵을 추가한다. 마지막 두 인자는 선택 사항이다. |
| **FullName** () | [[STRING\|STRING Object]] | 전체 가젯 이름을 가져온다. (예: '!!Form.gadget') |
| **Name** () | [[STRING\|STRING Object]] | 가젯의 이름을 가져온다. (예: 'gadget') |
| **Owner** () | FORM | 소유하고 있는 폼을 가져온다. |
| **SetPopup** (MENU menu) | NO RESULT | 주어진 메뉴를 가젯과 팝업으로 연결한다. |
| **RemovePopup** (MENU menu) | NO RESULT | 가젯에서 주어진 팝업 메뉴를 제거한다. |
| **GetPickedPopup** () | MENU | 팝업에서 선택된 메뉴의 이름을 반환한다. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | 표시 상태(shown status)를 가져온다. |
| **SetFocus** () | NO RESULT | 키보드 포커스를 이 가젯으로 이동한다. |
| **Refresh** () | NO RESULT | 가젯의 디스플레이를 새로 고친다. |
| **Background** () | [[STRING\|STRING Object]] | 배경 색상 이름을 가져온다. 일부 가젯(예: 픽스맵을 표시하는 가젯)은 모든 상황에서 이 속성을 지원하지 않는다. 색상이 명시적으로 설정되지 않은 가젯은 알려진 색상 이름을 갖지 않을 수 있으며, 이 경우 오류가 발생한다. |
| **SetToolTip** (STRING) | NO RESULT | 툴팁의 텍스트를 설정한다. |
| **Type** () | [[STRING\|STRING Object]] | 가젯 타입을 문자열로 가져온다. |

## 커맨드 (Commands)

```pml
BUTTON gname [ LINKLabel | TOGGLE ] tagtext
    AT ...
    CALLback text
    TOOLTIP text
    ANCHOR ...
    DOCK ...
    CORE
    FORM fname
    SIZE ...
    BACKGround colno
    PIXMAP size
    [ OK | APPLY | CANCEL | RESET | HELP ]
```

## 노트 (Notes)
1. 버튼은 Normal, Toggle, Linklabel 하위 유형(subtype)을 갖는다.
2. Linklabel은 버튼이므로 눌렸을 때 폼의 수정된 텍스트 필드에 대한 유효성 검사를 수행한다.
3. Linklabel은 다음과 같은 특징이 있다:
    1. 픽스맵을 할당할 수 없다.
    2. 배경 색상 변경을 지원하지 않는다.
    3. 'pressed' 및 'not pressed' 값을 지원하지 않는다.
    4. 상자(box)로 둘러싸여 있지 않다.
    5. 팝업 메뉴를 가질 수 있다 (권장되지는 않음).
    6. Control Types (예: OK, CANCEL 등)를 갖지 않는다.
4. 버튼 가젯의 하위 유형은 Button의 Subtype 메소드를 사용하여 쿼리할 수 있다.
5. 가젯을 정의할 때 나중에 추가할 가장 큰 픽스맵을 포함하도록 크기를 설정하는 것이 좋다. 이를 수행하지 않으면 예상치 못한 동작이 발생할 수 있다.
6. 과거에는 가젯이 비활성화되었을 때 사용되는 세 번째 픽스맵을 추가할 수 있었다. 가젯이 비활성화되면 픽스맵이 자동으로 회색 처리되므로 이 관행은 더 이상 필요하지 않다.