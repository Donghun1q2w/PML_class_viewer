---
tags: [PML2, E3D, VIEW, Gadget, 3D, Graphics, VOLUME]
aliases: [VIEW Gadget VOLUME Views Object, VOLUME View]
classification: Forms and Menu Objects & Gadgets
---

# [[VIEW Gadget: VOLUME Views]]

## 개요
VIEW ... VOLUME 명령은 View Setup 모드로 진입하게 합니다. 사용자는 EXIT 명령을 사용할 때까지 View Setup 모드에 머무르게 됩니다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Background** | [[REAL\|REAL Object]] | 배경 색상 번호를 설정하거나 가져옴. |
| **Background** | [[STRING\|STRING Object]] | 배경 색상 이름을 설정함 (Set Only). |
| **Contents** | REAL ARRAY[2] | 사용자 콘텐츠 ID를 설정하거나 가져옴. |
| **Defcall** | [[STRING\|STRING Object]] | 기본 상호작용 콜백(default interaction callback)을 설정하거나 가져옴. |
| **Height** | [[REAL\|REAL Object]] | 뷰 높이를 가져옴 (Get Only). |
| **Highlight** | [[REAL\|REAL Object]] | 강조(Highlight) 색상 번호를 설정하거나 가져옴. |
| **Highlight** | [[STRING\|STRING Object]] | 강조(Highlight) 색상 이름을 설정함 (Set Only). |
| **Prompt** | GADGET | 사용자 프롬프트 단락(paragraph) 가젯을 설정하거나 가져옴. |
| **Subtype** | [[STRING\|STRING Object]] | 그래픽 뷰의 하위 유형(Subtype)을 가져옴 (Get Only). |
| **Width** | [[REAL\|REAL Object]] | 뷰 너비를 가져옴 (Get Only). |
| **Borders** | [[BOOLEAN\|BOOLEAN Object]] | 테두리 표시 여부를 설정하거나 가져옴 (ON(TRUE) 또는 OFF(FALSE)). |
| **Direction** | REAL ARRAY[3] | 방향 벡터 [dE,dN,dU]를 설정하거나 가져옴. |
| **EyeMode** | [[BOOLEAN\|BOOLEAN Object]] | Eyemode인 경우 TRUE, Modelmode인 경우 FALSE를 설정하거나 가져옴. |
| **Limits** | REAL ARRAY[6] | 제한 상자(Limits box) [E1,E2,N1,N2,U1,U2]를 설정하거나 가져옴. |
| **Mousemode** | [[STRING\|STRING Object]] | 마우스 모드('ZOOM', 'PAN', 'ROTATE', 'WALK')를 설정하거나 가져옴. |
| **Projection** | [[STRING\|STRING Object]] | 투영 방식(‘PERSPECTIVE’ 또는 ‘PARALLEL’)을 설정하거나 가져옴. |
| **Radius** | [[REAL\|REAL Object]] | 뷰 반경(Radius) 거리를 설정하거나 가져옴 (\u003e0). |
| **Range** | [[REAL\|REAL Object]] | 범위(Range) 거리를 설정하거나 가져옴 (\u003e0). |
| **Refresh** | NO RESULT | 가젯의 표시를 새로 고침 (Get Only). |
| **RestoreView** | [[REAL\|REAL Object]] | 주어진 뷰 번호로 저장된 뷰를 복원함 (Get/Set). |
| **SaveView** | [[REAL\|REAL Object]] | 주어진 뷰 번호(범위 1~4)로 뷰를 저장함 (Get/Set). |
| **Shaded** | [[BOOLEAN\|BOOLEAN Object]] | 쉐이딩(Shaded)인 경우 TRUE, 와이어라인(wireline)인 경우 FALSE를 설정하거나 가져옴. |
| **Step** | [[REAL\|REAL Object]] | 단계(Step) 크기를 설정하거나 가져옴 (\u003e0). |
| **Through** | REAL ARRAY[3] | 통과점(Through point) [E,N,U]를 설정하거나 가져옴. |
| **WalkThrough** | [[BOOLEAN\|BOOLEAN Object]] | Walkthrough 모드 여부 (Eyemode와 동일) (TRUE/FALSE). |
| **LabelStyle** | [[STRING\|STRING Object]] | ‘ENU’ 또는 ‘XYZ’를 지정하여 설정함. 기본값은 ‘ENU’. |
| **Bearing** | [[REAL\|REAL Object]] | 뷰 방위각(Bearing) (-180 \u003c= bearing \u003c= 180). |
| **Elevation** | [[REAL\|REAL Object]] | 뷰 고도(Elevation) (-180 \u003c= elevation \u003c= 180). |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Background**() | [[STRING\|STRING Object]] | 배경 색상을 이름 문자열로 반환함. |
| **Highlight**() | [[STRING\|STRING Object]] | 강조(HIGHLIGHT) 색상을 이름 문자열로 반환함. |
| **SetSize**(REAL width, REAL height) | NO RESULT | 뷰 크기를 설정함. |
| **RestoreView**(REAL storeNumber) | NO RESULT | 주어진 뷰 번호로 저장된 뷰를 복원함. |
| **SaveView**(REAL storeNumber) | NO RESULT | 주어진 뷰 번호로 뷰를 저장함. |

## 커맨드 (Commands)

```
(VOLume)--+-- LOok --+-- \u003cdir\u003e ---------------------.
          |          |-- THRough---.                |
          |          |-- FROM -----|                |
          |          ‘-- TOWards --+-- \u003cpos\u003e ----.  |
          |                          |-- \u003cgid\u003e ----|  |
          |                          ‘-- ID @ NL --‘--|
          +-- ISOmetric --+-- value --.               |
          |               ‘-----------‘-------------|
          +-- PLAN ---------------------------------|
          +-- ELEVation -- (one of N/S/E/W/X/Y) ----|
          +-- CLIPping -----+-- ON --.              |
          |                   ‘-- OFF -‘--------------|
          +-- CAPping ------+-- ON --.              |
          |                   ‘-- OFF -‘--------------|
          +-- PERSPective --+-- ON --.              |
          |                   ‘-- OFF -‘--------------|
          +-- WALKthrough --+-- ON --.              |
          |                   ‘-- OFF -‘--------------|
          +--RADius --- value ----------------------|
          +--STEP ----- value ----------------------|
          ‘--RANGE ---- value ----------------------‘---\u003e
```

## 노트 (Notes)
- **Where:**
\t- `\u003ccolno\u003e`는 유효한 DESIGN 색상 정의(색상 설명 또는 색상 번호)입니다.
\t- `\u003ccursor\u003e`는 커서 유형을 선택하기 위한 구문입니다.
\t- `\u003cborder\u003e`는 줌(zooming)과 패닝(panning) 제어를 허용합니다.
- **Defaults:**
\t- Borders: ON
\t- Shading: OFF
\t- View direction: PLAN 또는 LOOK DOWN
\t- Limits: AUTO (현재 뷰 제한으로 설정됨)