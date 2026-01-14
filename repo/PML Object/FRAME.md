---
tags: [PML2, E3D, UI, Container, Gadget]
aliases: [FRAME Object]
classification: Forms and Menu Objects & Gadgets
---

# [[FRAME]]

## 개요
FRAME 명령은 프레임 가젯을 정의한다. 프레임은 다른 프레임을 포함하여 해당 범위 내에 정의된 모든 가젯을 소유하고 관리하는 컨테이너이다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Tag** | [[STRING\|STRING Object]] | 프레임에 제목으로 표시될 텍스트. |
| **Val** | [[REAL\|REAL Object]] | 정수 형태의 선택된 라디오 버튼 인덱스. |
| **RGroupCount** | [[REAL\|REAL Object]] | FRAME의 라디오 그룹 내 라디오 버튼(RTOGGLES)의 개수. FRAME이 라디오 그룹이 아닌 경우 0을 반환함. (Get only) |
| **Callback** | [[STRING\|STRING Object]] | 라디오 그룹 선택 콜백 문자열. |
| **Expanded** | [[BOOLEAN\|BOOLEAN Object]] | FoldUpPanel의 확장(expanded) 상태. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Rtoggle** (!index is REAL) | GADGET | !index 인덱스를 가진 RTOGGLE 가젯을 반환함. |
| **Background**() | [[STRING\|STRING Object]] | 배경 색상 이름(Background Colour Name)을 가져옴. (참고: 픽스맵을 표시하는 가젯 등 일부 가젯은 모든 상황에서 이 속성을 지원하지 않음. 색상이 명시적으로 설정되지 않아 알려진 색상 이름이 없는 경우 오류가 발생함). |

## 커맨드 (Commands)

```pml
\u003e--FRAME gname -+- TOOLBAR -+- tagtext -+- \u003ctoolbar\u003e -*
                |           ‘—- EXIT --\u003e
                | .---\u003c--------.
                |/             |
                +- TABSET -+-- \u003cfgpos\u003e ---|
                |          +-- \u003cfganch\u003e --|
                |          +-- \u003cfgdock\u003e --|
                |          +-- \u003cvshap\u003e ---*
                |          |  .---\u003c--------.
                |          |/              |
                |          +-- \u003ctabset\u003e --|
                |          +-- NL --------*
                |          ‘-- EXIT --\u003e
                +- PANEL --+----------.
                |          ‘--INDENT--|
                +- FOLDUPpanel -------| .---\u003c--------.
                                      |/             |
                                      +-- tagtext ---|
                                      +-- \u003cfgpos\u003e ---|
                                      +-- \u003cfganch\u003e --|
                                      +-- \u003cfgdock\u003e --|
                                      +-- \u003cvshap\u003e ---*
                                      |  .---\u003c--------.
                                      |/              |
                                      +-- \u003cformc\u003e ---*
                                      ‘-- EXIT --\u003e
```

## 노트 (Notes)
- 프레임에는 NORMAL, TABSET, TOOLBAR, PANEL, FOLDUP PANEL의 다섯 가지 유형이 있다.
- NORMAL 프레임은 다른 프레임을 포함한 모든 유형의 가젯을 포함할 수 있다. 또한 직접 포함하고 있는 RTOGGLE 가젯 세트에 의해 정의된 라디오 그룹으로도 동작한다.
- TABSET 프레임은 탭 페이지 FRAME만 포함할 수 있다. 이를 중첩할 수 없으며 이름이 없다.
- TOOLBAR 프레임은 BUTTON, TOGGLE, OPTION, TEXT 가젯 유형의 하위 집합만 포함할 수 있다. 이름이 있어야 하며 메인 폼(main forms)에만 나타날 수 있다.
- TABSET 프레임 내에 정의된 프레임 가젯은 NORMAL 타입이어야 하며, TOOLBAR나 TABSET일 수 없다. TABSET 프레임 바로 안에 정의된 NORMAL 프레임은 탭 페이지로 나타난다.
- PANEL 프레임 타입 선택 후에는 일반적인 방식으로 내용을 정의한다. Tagtext를 지정할 수 있지만 표시되지는 않는다. INDENT 옵션이 지정되지 않는 한 보이는 외곽선 박스가 없으며, 지정 시 3D 들여쓰기 모양을 갖는다. PANEL은 라디오 버튼 그룹의 개념을 포함하여 Normal Frame의 모든 속성을 지원한다.
- FOLDUP PANEL 선택 후 일반적인 방식으로 내용을 정의한다. 다른 FoldUpPanel을 제외한 일반적인 PML 가젯을 포함할 수 있다. 패널을 확장하거나 축소한 후 별도의 이벤트가 발생한다.
- FoldUpPanel의 기본 상태는 'expanded'(확장됨)이다. 패널이 확장되거나 축소될 때, 패널 아래에 있고 패널의 수평 범위 내(또는 부분적으로)에 있는 가젯들은 폼 아래나 위로 이동된다.
- FoldUpPanel인 프레임의 경우, 사용자가 패널을 대화형으로 접거나 펼칠 때마다 'HIDDEN' 및 'SHOWN' 이벤트가 발생한다. 이 이벤트들은 PML open callback이 정의된 경우에만 실행된다. 이는 FoldUpPanel 내의 라디오 버튼 선택을 알리는 데 사용되는 SELECT 이벤트가 여전히 단순한(non-Open) 콜백에 의해 처리될 수 있도록 보장한다. 라디오 그룹이기도 한 FoldUpPanel을 관리하려면 패널의 SELECT, HIDDEN, SHOWN 이벤트를 구분할 수 있도록 open callback을 제공해야 한다.
- 탭 페이지 프레임의 탭이 대화형으로 선택될 때, 현재 표시된 페이지가 숨겨질 때 HIDDEN 이벤트가 발생하고, 새로 선택된 페이지가 표시될 때 SHOWN 이벤트가 발생한다. 이 이벤트들은 PML open callback이 할당된 경우에만 발생한다.