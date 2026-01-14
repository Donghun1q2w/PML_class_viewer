---
tags: [PML2, E3D, Form, Gadget, Layout, .NET, Hosting]
aliases: [CONTAINER Gadget]
classification: Forms and Menu Objects & Gadgets
---

# [[CONTAINER Gadget]]

## 개요
Container 가젯은 PML 정의 폼 내에서 PMLNet 컨트롤과 같은 외부 컨트롤을 호스팅할 수 있게 해줍니다. 사용자가 외부 .Net 컨트롤을 추가하여 PML에서 이벤트를 처리할 수 있도록 하며, .Net 컨트롤의 'popup' 이벤트 발생 시 표시될 PML 팝업 메뉴를 할당할 수 있습니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **type** | STRING Get/Set | 가젯 타입을 문자열 'Container'로 반환합니다. |
| **control** | REAL Get/Set | 외부 컨트롤의 정수 핸들(handle)입니다. |
| **popup** | MENU Get/Set | 컨트롤과 연관된 팝업 메뉴입니다. |

## 메소드 (Methods)

| Name                                   | Result    | Purpose                                            |
| :------------------------------------- | :-------- | :------------------------------------------------- |
| **ShowPopup** (!x is REAL, !y is REAL) | NO RESULT | 지정된 위치에 연관된 팝업을 표시합니다. 위치는 포함된 컨트롤 내의 정수 픽셀 위치입니다. |

## 커맨드 (Commands)

```
\u003e---- CONTAINER gname -+- NOBOX ---|
                        +- INDENT --*
                        | 
                        '- PMLNET/CONTROL -+- handle -.
                                           '----------|
                          .----\u003c----------------------*
                          | 
                          | .----\u003c-----------------.
                          |/                       |
                          +-- tagtext -------------|
                          +-- \u003cfgpos\u003e -------------|
                          +-- \u003cfganch\u003e ------------|
                          +-- \u003cfgdock\u003e ------------*
                          | 
                          +-- \u003cvshap\u003e -.
                          '------------'--\u003e
```

## 노트 (Notes)
1. 기본적으로 Container는 박스로 둘러싸여 있지만, NOBOX 또는 INDENT를 선택할 수 있습니다.
2. PMLNet 컨트롤만 지원됩니다.
3. 'handle'은 컨트롤을 식별하는 정수 토큰입니다.
4. 위치 지정(Positioning)은 크기(\u003cvshap\u003e) 이전에 지정해야 합니다.
5. 지능형 리사이즈 동작을 허용하기 위해 Dock과 Anchor가 지원됩니다. 포함된 컨트롤은 리사이즈를 지원해야 하며 일반적으로 Dock fill로 설정되어 Container의 크기 변경을 따르도록 합니다.