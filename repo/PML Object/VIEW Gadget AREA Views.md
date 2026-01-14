---
tags: [PML2, E3D, Gadget, Form, View, Graphics, AREA]
aliases: [VIEW Gadget: AREA View Object]
classification: Forms and Menus Objects
---

# [[VIEW Gadget: AREA View]]

## 개요
VIEW ... AREA 명령은 View Setup 모드로 진입하게 한다. 사용자는 EXIT 명령을 사용할 때까지 View Setup 모드에 머무르게 된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Limits** | REAL ARRAY[4] | 한계(limits) 상자 [x1,y1,x2,y2]를 가져오거나 설정한다. |
| **Borders** | [[BOOLEAN\|BOOLEAN Object]] | 테두리(borders)의 ON(TRUE) 또는 OFF(FALSE) 여부를 가져오거나 설정한다. |
| **Background** | [[REAL\|REAL Object]] | 배경(background) 색상 번호를 가져오거나 설정한다. |
| **Background** | [[STRING\|STRING Object]] | 배경(background) 색상 이름을 설정한다. (설정 전용) |
| **Contents** | REAL ARRAY[2] | 사용자 콘텐츠 ID를 가져오거나 설정한다. |
| **Defcall** | [[STRING\|STRING Object]] | 기본 상호작용 콜백(callback)을 가져오거나 설정한다. |
| **Height** | [[REAL\|REAL Object]] | 뷰의 높이를 가져온다. (읽기 전용) |
| **Highlight** | [[REAL\|REAL Object]] | 강조(highlight) 색상 번호를 가져오거나 설정한다. |
| **Highlight** | [[STRING\|STRING Object]] | 강조(highlight) 색상 이름을 설정한다. (설정 전용) |
| **Prompt** | GADGET | 사용자 프롬프트 PARAGRAPH 가젯을 가져오거나 설정한다. |
| **Subtype** | [[STRING\|STRING Object]] | 그래픽 뷰의 하위 유형(subtype)을 가져온다. (읽기 전용) |
| **Width** | [[REAL\|REAL Object]] | 뷰의 너비를 가져온다. (읽기 전용) |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Background** () | [[STRING\|STRING Object]] | 강조(highlight) 색상을 이름 문자열로 반환한다. |
| **Clear** () | NO RESULT | VIEW 콘텐츠를 지운다. |
| **Highlight** () | [[STRING\|STRING Object]] | 강조(highlight) 색상을 이름 문자열로 반환한다. |
| **Refresh** () | NO RESULT | 가젯의 표시를 새로 고친다. |
| **RestoreView** (REAL storeNumber) | NO RESULT | 지정된 저장 번호(store number)로 저장된 VIEW를 복원한다. |
| **SaveView** (REAL storeNumber) | NO RESULT | 현재 VIEW를 저장한다. 번호는 1에서 4 사이여야 한다. |
| **SetSize** (REAL width, REAL height) | NO RESULT | VIEW 크기를 설정한다. |

## 커맨드 (Commands)

```text
.-------------------------\u003c-------------------------.
/                                                   |
(AREa) --+- \u003cvshap\u003e -----------------------------------.    |
         +- PUT - \u003csgid\u003e ------------------------------|    |
         +- LIMits \u003cuval\u003e \u003cuval\u003e - TO - \u003cuval\u003e \u003cuval\u003e -|    |
         +- SETColour - \u003ccolno\u003e -----------------------|    |
         +- SETHighlight - \u003ccolno\u003e --------------------‘- NL -|
         +- \u003ccursor\u003e -----------------------------------------|
         +- \u003cborder\u003e -----------------------------------------|
         +-- \u003cpml\u003e -------------------------------------------*
         ‘-- EXIT --\u003e
```