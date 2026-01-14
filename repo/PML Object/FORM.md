---
tags: [PML2, E3D, UI, GUI, Form, Container]
aliases: [FORM Object]
classification: Forms and Menus Objects
---

# [[FORM]]

## 개요
폼(Form) 정의는 `SETUP FORM` 명령으로 시작하여 해당 `EXIT` 명령으로 종료됩니다. Form Setup 모드에서는 폼의 속성을 정의하고, 메뉴 바, 메인 및 팝업 메뉴, 그리고 폼이 소유할 가젯들을 생성하는 명령을 호출할 수 있습니다. 한 번 설정되는(Once-only) 폼 속성은 `SETUP FORM` 명령 라인의 일부로 입력되며, 수정 가능한 속성은 폼의 내용으로 입력됩니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **FormRevision** | [[STRING\|STRING Object]] | Form Revision 텍스트. |
| **FormTitle** | [[STRING\|STRING Object]] | 폼 제목. |
| **IconTitle** | [[STRING\|STRING Object]] | 아이콘 제목. |
| **Initcall** | [[STRING\|STRING Object]] | 폼이 초기화될 때 실행되는 콜백. |
| **Autocall** | [[STRING\|STRING Object]] | 지정된 애플리케이션 속성이 변경되었을 때 실행되는 콜백. |
| **Okcall** | [[STRING\|STRING Object]] | OK 버튼이 눌렸을 때 실행되는 콜백. |
| **Cancelcall** | [[STRING\|STRING Object]] | CANCEL 버튼이 눌렸을 때 실행되는 콜백. |
| **KeyboardFocus** | GADGET | 폼이 표시될 때 초기 키보드 포커스를 가질 가젯. TEXTFIELD, TEXTPANE, BUTTON, TOGGLE 또는 ALPHA VIEW 중 하나. |
| **AutoScroll** | [[BOOLEAN\|BOOLEAN Object]] | AutoScroll이 선택되면 폼의 크기가 정의된 내용을 표시하기에 너무 작아질 경우 자동으로 수평 또는 수직 스크롤바가 생김. 이 멤버는 Main Window 및 Document 유형의 폼에는 적용되지 않음. |
| **Quitcall** | [[STRING\|STRING Object]] | 사용자가 폼이나 메인 애플리케이션 창의 타이틀 바에서 종료/닫기 아이콘(X)을 누를 때 실행되는 콜백. MAIN 유형의 폼에서는 사용자가 애플리케이션을 종료할 수 있도록 하며, 다른 폼 유형에서는 폼과 자식 폼을 숨김(Hide). |
| **Maximised** | [[BOOLEAN\|BOOLEAN Object]] | 폼의 최대화 상태(화면상)를 가져오거나 설정함. |
| **Active** | [[BOOLEAN\|BOOLEAN Object]] | 폼의 활성/비활성 상태를 제공함. (Get Only) |
| **Popup** | MENU | 폼의 현재 팝업 메뉴를 가져오거나 설정함. |
| **HelpContextID** | [[STRING\|STRING Object]] | 이 폼에 대한 도움말 파일 내의 컨텍스트 ID를 설정하거나 가져옴. |
| **Killingcall** | [[STRING\|STRING Object]] | 폼이 파괴되고 있음을 알리고, 할당된 콜백 메소드가 관련 리소스(예: 파괴되지 않을 수 있는 전역 PML 객체)를 파괴할 수 있도록 함. |
| **FirstShowncall** | [[STRING\|STRING Object]] | 폼이 실제로 처음 표시될 때만 완료될 수 있는 폼 작업을 사용자가 수행할 수 있도록 허용함. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Name** () | [[STRING\|STRING Object]] | 이름을 가져옴. |
| **FullName** () | [[STRING\|STRING Object]] | 전체 폼 이름(!! 포함)을 가져옴. |
| **NewMenu** (STRING menuname) | MENU | 폼에 새로운 이름의 메뉴를 추가함. |
| **NewMenu** (STRING menuname, STRING type) | MENU | 폼에 새로운 이름과 유형의 메뉴를 추가함. 첫 번째 인수는 새 메뉴의 이름이고, 두 번째 인수는 메뉴의 유형으로 'POPUP' 또는 'MAIN'이어야 함. |
| **SetActive** (BOOLEAN) | NO RESULT | SetActive(FALSE)는 폼의 모든 가젯을 회색으로 표시(grey-out)하지만 Active 상태를 설정하지는 않으므로, SetActive(TRUE)는 폼을 회색으로 표시하기 전의 정확한 상태로 복원함(즉, 비활성 가젯은 여전히 비활성 상태 유지). |
| **SetGadgetsActive** (BOOLEAN) | NO RESULT | SetGadgetsActive(FALSE)는 폼의 모든 가젯을 회색으로 표시하고 Active 상태를 'inactive'로 설정함(이전 active 상태 손실). 마찬가지로 SetGadgetsActive(TRUE)는 모든 가젯의 회색 표시를 해제하고 Active 상태를 'active'로 설정함. |
| **SetPopup** (MENU) | NO RESULT | 폼 배경에서 마우스 오른쪽 버튼을 놓을 때 표시될 팝업을 지정함. |
| **RemovePopup** (MENU) | NO RESULT | 폼과 연관된 팝업을 제거함. |
| **GetPickedPopup** () | MENU | 폼에 대해 마지막으로 선택된 팝업 메뉴를 반환함. |
| **Show** ('FREE') | NO RESULT | 폼을 화면에 FREE 폼으로 표시함. |
| **Show** ('AT', REAL X, REAL Y) | NO RESULT | 폼을 X,Y 상대 화면 위치에 원점을 둔 FREE 폼으로 표시함. |
| **Show** ('CEN', REAL X, REAL Y) | NO RESULT | 폼을 X,Y 상대 화면 위치에 중심을 둔 FREE 폼으로 표시함. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | 'shown' 상태를 가져옴. |
| **Hide** () | NO RESULT | 폼을 숨김 (화면에서 제거). |
| **Owner** () | FORM | 폼의 부모 폼을 반환하거나, 폼이 독립형(free-standing)인 경우 설정되지 않은(unset) 변수를 반환함. |
| **SetOpacity** ( REAL PERCENT ) | NONE | 폼의 불투명도(opaqueness) 비율을 10(거의 투명)에서 100(불투명 - 기본값) 사이의 정수로 설정함. 도킹되지 않는 Dialog 및 BlockingDialog 폼 유형에만 유효함. |
| **Subtype** ( ) | [[STRING\|STRING Object]] | 폼의 하위 유형을 가져옴. 'DIALOG', 'BLOCKINGDIALOG', 'MAIN', 'DOCUMENT' 중 하나. |

## 커맨드 (Commands)

```
SETUP FORM fname --+-- MAIN -----+-------------------------------|
                   +-- DOCUMENT -+- FLOAT -----------------------|
                   |             ‘-------------------------------|
                   +-- DIALOG ---+- DOCKing -+-------------------|
                   |             |           |- Left ---.        |
                   |             |           |- Right --|        |
                   |             |           |- Top ----|        |
                   |             |           ‘- Bottom -‘--------|
                   |             |- RESIzeable ------------------|
                   |             ‘-------------------------------|
                   +-- BLOCKingdialog -+- RESIzeable ------------|
                   |                   ‘-------------------------|
                   +-- VARCHARS ---------------------------------|
                   +-- FIXCHARS ---------------------------------|
                   +-- AT \u003cxypos\u003e -------------------------------|
                   +-- SIZE val val -----------------------------|
                   +-- NOQUIT -----------------------------------|
                   +-- NOALIGN ----------------------------------|
                   +-- CORE -------------------------------------*
                   |                 .---\u003c------.
                   |                |/          |
                   +-- \u003cform\u003e --*    form contents
                   ‘—EXIT --\u003e
```

```
TITLE text
```

```
CANCELcall text
```

```
CURSortype --+-- POINTER ----.
             +-- NOCURSOR ---|
             +-- PICK -------|
             +-- PICKPLUS ---|
             ‘-- CROSSHAIR --‘--\u003e
```

```
ICONTItle text
```

```
INITcall text
```

```
OKcall text
```

```
PATH --+-- Up ------.
       +-- Down ----|
       +-- Left ----|
       ‘-- Right ---‘--\u003e
```


```
HAlign --+-- Left ----.
         +-- Centre --|
         ‘-- Right ---‘--\u003e
```

```
HDistance value
```

```
VAlign --+-- Top -----.
         +-- Centre --|
         ‘-- Bottom --‘--\u003e
```

```
VDistance value
```

## 노트 (Notes)
- SetActive()와 SetGadgetsActive()는 서로 조합하거나 개별 가젯의 Active 속성과 조합하여 사용할 수 있다.
- 가젯을 다른 가젯 위에 배치하는 것은 좋지 않은 관행이다. 이는 가젯이 가려지는 결과를 초래할 수 있다.
- BUTTON, TOGGLE, TEXT, OPTION, 한 줄 PARAGRAPH와 같은 가젯은 기본적으로 인접한 BUTTON과 중앙 정렬되도록 Y 좌표가 조정된다. NOALIGN은 이러한 (과거의) 가젯 자동 정렬을 방지한다.
- Load, Activate, Kill 이벤트는 폼의 수명 동안 한 번만 발생한다.
- Show와 Hide는 반복적으로 발생할 수 있다.
- 폼의 생성자(Constructor)는 한 번만 실행된다.
- FirstShown 이벤트는 한 번만 발생한다.
- INIT은 매 Show마다 발생한다.
- KILLING 콜백 메소드는 폼이나 폼에 속한 가젯에 대해 어떠한 수정도 수행해서는 안 된다(예: 폼을 show하거나 hide하지 말 것). 폼이나 가젯을 편집하려고 하면 원치 않는 부작용이나 시스템 오류가 발생할 수 있다.