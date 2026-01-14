---
tags: [PML2, E3D, GUI, Gadget, View, Alpha]
aliases: [ALPHA Views Object]
classification: Forms and Menus Objects
---

# [[VIEW Gadget: ALPHA Views]]

## 개요
VIEW ... ALPHA 명령은 View Setup 모드로 진입하게 하며, EXIT 명령을 사용할 때까지 해당 모드가 유지됩니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Channel** | [[STRING\|STRING Object]] | 할당된 채널을 가져오거나 설정합니다. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Clear**() | NO RESULT | Alpha TTY 창의 모든 라인을 지웁니다. |
| **Refresh**() | NO RESULT | 가젯의 표시를 새로 고칩니다. |
| **SetFocus**() | NO RESULT | 키보드 포커스를 즉시 이 Alpha 가젯으로 설정합니다. |
| **removeRequests**() | NO RESULT | Alpha view 가젯에서 ‘requests’ 채널을 삭제하고, 필요한 경우 현재 Requests IO-channel과의 연결을 해제합니다. |
| **Background**() | [[STRING\|STRING Object]] | 배경 색상 이름(Background Colour Name)을 가져옵니다. 일부 가젯은 모든 상황(예: 픽스맵을 표시하는 가젯)에서 이 속성을 지원하지 않습니다. 색상이 명시적으로 설정되지 않은 가젯은 알려진 색상 이름을 갖지 않을 수 있습니다. 이 경우 오류가 발생합니다. |

## 커맨드 (Commands)

```pml
(ALPha)--+- \u003cvshap\u003e -----------------------------------. 
         +- CHANNEL -+- COMMANDS -----------------------| 
         |           ‘- REQUESTS -----------------------‘- NL -*
         ‘-- EXIT --\u003e
```