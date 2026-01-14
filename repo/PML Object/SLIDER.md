---
tags: [PML2, E3D, Gadget, UI, Form]
aliases: [SLIDER Object]
classification: Forms and Menu Objects & Gadgets
---

# [[SLIDER]]

## 개요
Val 멤버는 슬라이더의 현재 값을 PML REAL(실제로는 항상 정수)로 나타냅니다. Range 멤버를 통해 슬라이더 범위와 선택적으로 단계(step) 값을 설정하거나 조회할 수 있습니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **visible** | [[BOOLEAN\|BOOLEAN Object]] | 가시성 (Visibility). |
| **active** | [[BOOLEAN\|BOOLEAN Object]] | 활성 (회색 처리된) 상태 (Active (greyed-in) status). |
| **callback** | [[STRING\|STRING Object]] | 콜백 문자열. |
| **tag** | [[STRING\|STRING Object]] | 태그 텍스트 - 이 가젯에는 표시되지 않음. |
| **val** | [[REAL\|REAL Object]] | 정수 형태의 현재 값. |
| **background** | [[REAL\|REAL Object]] | 배경 색상 번호 (Set/Get). |
| **background** | [[STRING\|STRING Object]] | 배경 색상 이름 (Set only). |
| **range** | REAL ARRAY | 범위 시작, 종료 및 선택적 단계(\u003e0)를 정수로 지정. 시작 값은 종료 값보다 작을 수 있음. 배열 크기는 2 이상이어야 함. |
| **tickstyle** | [[REAL\|REAL Object]] | 정수 형태의 눈금 스타일.\u003cbr\u003e0 - 없음, 1 - 오른쪽 또는 아래쪽, 2 - 위쪽 또는 왼쪽, 3 - 1과 2 모두. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **FullName** () | [[STRING\|STRING Object]] | 전체 가젯 이름 반환 (예: '!!Form.gadget'). |
| **Name** () | [[STRING\|STRING Object]] | 가젯의 이름 반환 (예: 'gadget'). |
| **Owner** () | FORM | 소유 양식(Form) 반환. |
| **SetToolTip** (STRING) | NO RESULT | 툴팁 텍스트를 설정하거나 편집함. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | '표시(shown)' 상태 반환. |
| **Type** () | [[STRING\|STRING Object]] | 가젯 유형을 문자열(예: 'SLIDER')로 반환. |
| **Refresh** () | NO RESULT | 가젯 이미지 새로 고침. |
| **Background** () | [[STRING\|STRING Object]] | 배경 색상 이름 반환.\u003cbr\u003e일부 가젯(예: 픽스맵이 표시되는 가젯)은 모든 상황에서 이 속성을 지원하지 않음. 가젯의 색상이 명시적으로 설정되지 않은 경우, 알려진 색상 이름을 가지지 않을 수 있으며 이 경우 오류가 발생함. |
| **SetFocus** () | NO RESULT | 가젯에 키보드 포커스 설정. 화살표 키로 슬라이더를 구동할 수 있음. |

## 커맨드 (Commands)

```
\u003e-- SLIDER gname -+- tagtext -------------------|
                  +- \u003cfgpos\u003e -------------------|
                  +- CORE ----------------------| Core managed gadget
                  +- \u003cfganch\u003e ------------------|
                  +- \u003cfgdock\u003e ------------------|
                  +- BACKGround \u003ccolno\u003e --------|
                  +- CALLback text -------------|
                  +- TOOLTIP text --------------|
                  +- VERTical ------------------|
                  +- HORIZontal ----------------*
                  |
                  | .-------\u003c-------------------.
                  |/                            |
                  +- RANGE int int -------------|
                  +- STEP int ------------------|
                  +- VALue int -----------------*
                  |
                  ‘- \u003cvshap\u003e -+- TOOLTIP text -.
                              ‘----------------‘--\u003e
```

## 노트 (Notes)
- Val 멤버는 슬라이더의 현재 값을 PML REAL(실제로는 항상 정수)로 나타냅니다.
- Range 멤버를 통해 슬라이더 범위와 선택적으로 단계(step) 값을 설정하거나 조회할 수 있습니다. 슬라이더 이동의 세분성은 지정된 단계 증가값에 의해 결정됩니다. 즉, 슬라이더 범위 내에서 각 단계 증가값마다 이동 이벤트가 발생합니다. 범위 제한은 단계 크기의 정수배여야 합니다(그렇지 않으면 오류가 표시됨).
- 양식(Form)의 RESET 액션(reset, CANCEL 또는 QUIT 액션으로부터 발생)은 슬라이더의 현재 값만 재설정하며 다른 슬라이더 속성은 재설정하지 않습니다. 따라서 양식이 표시된 상태에서 범위를 재정의하고 RESET 버튼을 누르면, 범위는 이전 설정으로 되돌아가지 않습니다. 리셋 버튼의 콜백 및/또는 양식의 CANCELCALL 콜백에서 이를 수행해야 합니다.
- 눈금(Tick marks)이 있는 경우 범위 내의 모든 단계 값마다 발생합니다.
- 사용자는 범위를 시작(start), 종료(end) 및 선택적인 단계(step)와 값(value) 정수값으로 지정할 수 있습니다.
- `\u003cvshap\u003e` 그래프는 슬라이더의 너비(WIDTH) 및/또는 높이(HEIGHT)를 그리드 단위로 지정할 수 있게 합니다. 수평 슬라이더의 경우 너비를 지정해야 하며, 수직 슬라이더의 경우 높이를 지정해야 합니다. 다른 차원이 지정되지 않은 경우 기본 크기가 가정됩니다.
- 태그 텍스트는 슬라이더 가젯에 표시되지 않습니다.