---
tags: [PML2, E3D, Forms, Menus, Gadgets]
aliases: [ALERT Object]
classification: Forms and Menu Objects & Gadgets
---

# [[ALERT]]

## 개요
ALERT Object는 차단(blocking) CONFIRM, ERROR, MESSAGE, QUESTION, WARNING, INPUT 알림 창을 표시하고 사용자의 응답을 가져오는 데 사용된다. 각 메소드는 알림 창의 유형에 따라 적절한 문자열(STRING) 결과를 반환한다.

## 메소드 (Methods)

| Name | Result | Purpose |
|:---|:---|:---|
| **Confirm** ( Message is STRING, X is REAL, Y is REAL ) | [[STRING\|STRING Object]] | 차단(blocking) CONFIRM ALERT를 표시하고 응답을 가져온다. X와 Y는 선택적인 화면 위치다. 결과값은 'YES' 또는 'NO'이다. |
| **Error** (Message is STRING, X is REAL, Y is REAL ) | [[STRING\|STRING Object]] | 차단(blocking) ERROR ALERT를 표시하고 응답을 가져온다. X와 Y는 선택적인 화면 위치다. 결과값은 'YES'이다. |
| **Message** (Message is STRING, X is REAL, Y is REAL) | [[STRING\|STRING Object]] | 차단(blocking) MESSAGE ALERT를 표시하고 응답을 가져온다. X와 Y는 선택적인 화면 위치다. 결과값은 'YES'이다. |
| **Question** (Message is STRING, X is REAL, Y is REAL ) | [[STRING\|STRING Object]] | 차단(blocking) QUESTION ALERT를 표시하고 응답을 가져온다. X와 Y는 선택적인 화면 위치다. 결과값은 'YES', 'NO' 또는 'CANCEL'이다. |
| **Warning** (Message is STRING, X is REAL, Y is REAL) | [[STRING\|STRING Object]] | 차단(blocking) WARNING ALERT를 표시하고 응답을 가져온다. X와 Y는 선택적인 화면 위치다. 결과값은 'YES'이다. |
| **Input** ( !prompt is STRING, !default is STRING) | [[STRING\|STRING Object]] | 차단(blocking) INPUT ALERT를 표시한다. !prompt는 사용자에게 표시되는 프롬프트이고, !default는 텍스트 상자의 기본값이다. |
| **Input** ( !prompt is STRING, !default is STRING, xPos is REAL, yPos is REAL) | [[STRING\|STRING Object]] | 차단(blocking) INPUT ALERT를 표시한다. !prompt는 사용자에게 표시되는 프롬프트이고, !default는 텍스트 상자의 기본값이다. xPos와 yPos는 알림 상자의 좌측 상단 모서리 좌표다. |