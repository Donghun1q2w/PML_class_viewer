---
tags: [PML2, E3D, Gadget, Form]
aliases: [SLIDER Object]
classification: Forms and Menu Objects & Gadgets
---

# [[SLIDER Gadget]]

## 개요
SLIDER 명령은 슬라이더 가젯을 정의하며, 위치, 태그, 범위, 단계 및 초기 값을 지정한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **visible** | [[BOOLEAN\|BOOLEAN Object]] | 가시성 (Visibility). |
| **active** | [[BOOLEAN\|BOOLEAN Object]] | 활성 (회색 표시) 상태. |
| **callback** | [[STRING\|STRING Object]] | 콜백 문자열. |
| **tag** | [[STRING\|STRING Object]] | 태그 텍스트 - 이 가젯에는 표시되지 않음. |
| **val** | [[REAL\|REAL Object]] | 현재 값 (정수). |
| **background** | [[REAL\|REAL Object]] | 배경 색상 번호 설정 또는 가져오기. |
| **background** | STRING (Set only) | 배경 색상 이름 설정. |
| **range** | REAL ARRAY | 범위 시작(Start), 종료(End) 및 선택적 단계(Step, \u003e0)를 정수로 지정한다. 시작 값은 종료 값보다 작을 수 있다. 배열 크기는 2 이상이어야 한다. |
| **tickstyle** | [[REAL\|REAL Object]] | 틱(Tick) 스타일 (정수).\u003cbr\u003e0 - 없음, 1 - 오른쪽 또는 아래쪽, 2 - 위쪽 또는 왼쪽, 3 - 1과 2 모두. |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **FullName**() | [[STRING\|STRING Object]] | 전체 가젯 이름을 가져온다 (예: '!!Form.gadget'). |
| **Name**() | [[STRING\|STRING Object]] | 가젯의 이름을 가져온다 (예: 'gadget'). |
| **Owner**() | FORM | 소유하고 있는 폼(form)을 가져온다. |
| **SetToolTip**(STRING) | NO RESULT | 툴팁(Tooltip) 텍스트를 설정하거나 편집한다. |
| **Shown**() | [[BOOLEAN\|BOOLEAN Object]] | '표시(shown)' 상태를 가져온다. |
| **Type**() | [[STRING\|STRING Object]] | 가젯 타입을 문자열로 가져온다 (예: 'SLIDER'). |
| **Refresh**() | NO RESULT | 가젯 이미지를 새로 고친다. |
| **Background**() | [[STRING\|STRING Object]] | 배경 색상 이름을 가져온다.\u003cbr\u003e일부 가젯(예: 픽스맵을 표시하는 가젯)은 모든 상황에서 이 속성을 지원하지 않는다. 색상이 명시적으로 설정되지 않은 가젯은 알려진 색상 이름을 갖지 않을 수 있으며, 이 경우 오류가 발생한다. |
| **SetFocus**() | NO RESULT | 키보드 포커스를 가젯으로 설정한다. 화살표 키로 슬라이더를 조작할 수 있게 한다. |

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
- **Val** 멤버는 슬라이더의 현재 값을 PML REAL(실제로는 항상 정수)로 나타낸다.
- **Range** 멤버를 통해 슬라이더 범위와 선택적으로 단계(step) 값을 설정하거나 쿼리할 수 있다. 슬라이더 이동의 세분성(granularity)은 지정된 단계 증분값에 의해 결정된다. 즉, 슬라이더 범위 내에서 각 단계 증분마다 이동 이벤트가 생성된다. 범위 제한은 각각 단계 크기의 정수 배수여야 한다(그렇지 않으면 오류 플래그가 지정됨).
- 폼의 RESET 액션(reset, CANCEL 또는 QUIT 액션에서 발생)은 슬라이더의 현재 값만 재설정하고 다른 슬라이더 속성은 재설정하지 않는다. 따라서 폼이 표시되는 동안 범위를 재정의하고 RESET 버튼을 누르면, 범위가 이전 설정으로 되돌아가지 않는다. 리셋 버튼의 콜백 및/또는 폼의 CANCELCALL 콜백에서 이를 수행해야 한다.
- 틱 마크(Tick marks)가 존재하는 경우 범위 내의 모든 단계(step) 값마다 발생한다.
- 사용자는 start, end 및 선택적 step과 value 정수 값으로 범위를 지정할 수 있다.
- `\u003cvshap\u003e` 그래프를 사용하면 그리드 단위로 슬라이더의 WIDTH 및/또는 HEIGHT를 지정할 수 있다. 수평 슬라이더의 경우 너비를 지정해야 하며, 수직 슬라이더의 경우 높이를 지정해야 한다. 다른 치수가 지정되지 않으면 기본 크기가 가정된다.
- 슬라이더 가젯에는 태그 텍스트가 표시되지 않는다.