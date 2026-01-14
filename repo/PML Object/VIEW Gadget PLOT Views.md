---
tags: [PML2, E3D, VIEW, PLOT, Gadget]
aliases: [VIEW Gadget: PLOT View Object]
classification: Forms and Menu Objects & Gadgets
---

# [[VIEW Gadget: PLOT View]]

## 개요
VIEW ... PLOT 명령은 View Setup 모드로 진입하게 합니다. EXIT 명령을 사용할 때까지 View Setup 모드에 남아있게 됩니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Background** | [[REAL\|REAL Object]] | 배경 색상 번호(Colour Number)를 가져오거나 설정한다. |
| **Background** | [[STRING\|STRING Object]] | 배경 색상 이름(Colour Name)을 설정한다. (Set Only) |
| **Borders** | [[BOOLEAN\|BOOLEAN Object]] | 테두리 켜기(TRUE) 또는 끄기(FALSE)를 가져오거나 설정한다. |
| **Contents** | REAL ARRAY[2] | 사용자 컨텐츠 ID를 가져오거나 설정한다. |
| **Defcall** | [[STRING\|STRING Object]] | 기본 상호작용 콜백(default interaction callback)을 가져오거나 설정한다. |
| **Height** | [[REAL\|REAL Object]] | 뷰 높이를 가져온다. (Get Only) |
| **Highlight** | [[REAL\|REAL Object]] | 하이라이트 색상 번호(highlight Colour Number)를 가져오거나 설정한다. |
| **Highlight** | [[STRING\|STRING Object]] | 하이라이트 색상 이름(highlight Colour Name)을 설정한다. (Set Only) |
| **Prompt** | GADGET | 사용자 프롬프트 PARAGRAPH 가젯을 가져오거나 설정한다. |
| **Subtype** | [[STRING\|STRING Object]] | 그래픽 뷰의 하위 유형(subtype)을 가져온다. (Get Only) |
| **Width** | [[REAL\|REAL Object]] | 뷰 너비를 가져온다. (Get Only) |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Add** (STRING) | NO RESULT | STRING으로 주어진 이름의 플롯 파일을 추가한다. 주어진 플롯 파일이 있다면 대체한다. |
| **Background**() | [[STRING\|STRING Object]] | 배경 색상을 이름 STRING으로 반환한다. |
| **Clear**() | NO RESULT | 가젯 컨텐츠를 지운다. |
| **Highlight**() | [[STRING\|STRING Object]] | 하이라이트 색상을 이름 STRING으로 반환한다. |
| **Refresh**() | NO RESULT | 가젯의 표시를 새로 고친다. |
| **SetSize**(REAL width, REAL height) | NO RESULT | 뷰 크기를 설정한다. |

## 커맨드 (Commands)

```text
.-------------------------\u003c------------------------.
/                                                  |
(PLOT) --+- \u003cvshap\u003e -----------------------------------. |
         +- ADD - plot_filename -----------------------| |
         +- CLear -------------------------------------| |
         +- SETColour - \u003ccolno\u003e -----------------------| |
         +- SETHighlight - \u003ccolno\u003e --------------------‘- NL -|
         +- \u003ccursor\u003e -----------------------------------------|
         +- \u003cborder\u003e -----------------------------------------|
         +-- \u003cpml\u003e -------------------------------------------*
         ‘-- EXIT --\u003e
```

where:
*   `\u003ccolno\u003e` is any valid PDMS colour definition.
*   `\u003ccursor\u003e` is the syntax for selecting the cursor type.
*   `\u003cborder\u003e` allows control of zooming and panning.