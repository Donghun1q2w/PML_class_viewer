---
tags: [PML2, E3D, Draft, 3D_View, Section_Plane]
aliases: [Section Plane Object]
classification: PDMS Objects
---

# [[Section Plane]]

## 개요
Section Plane(절단 평면) 오브젝트는 Draft의 3D View에서 절단 평면을 조회하고 수정하기 위한 인터페이스를 제공한다. 이 오브젝트는 PMLSectionPlaneManager PML 오브젝트와 함께 사용할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **sectionPlane** (DBREF) | constructor | 주어진 DBREF로 Section Plane Object를 생성한다. DBREF는 반드시 SPLA, PPLA, 또는 FPLA 요소를 나타내야 한다. |
| **Redraw** () | No Result | 3D View에서 평면을 다시 그린다. 평면은 두 방향으로 무한하지만, 현재 drawlist의 가장자리에 맞춰 잘린 무한한 가장자리(infinite edges)로 그려진다. 따라서 평면이 이동하거나 drawlist가 변경되면 평면을 다시 그려야 할 수 있다. |
| **Highlight** () | No Result | 3D View에서 절단 평면(Section Plane)을 일시적으로 강조 표시한다. |
| **Show** (BOOLEAN) | No Result | 3D View에서 평면을 표시하거나 숨긴다. |
| **setClipping** (BOOLEAN, DBREF) | No Result | VIEW 내에서 절단 평면의 클리핑 상태를 설정/해제한다. DBREF는 VIEW 요소의 참조이다. |
| **switchClipside** (DBREF) | No Result | 모델이 절단 평면의 어느 쪽에서 클리핑될지에 대해 표준(standard)과 반대(reverse) 사이를 전환한다. DBREF는 VIEW 요소의 참조이다. |
| **showClipItems** (BOOLEAN, DBREF) | No Result | 이 절단 평면의 클립 목록에 있는 항목을 3D View에서 강조 표시한다. DBREF는 VIEW 요소의 참조이다. |
| **redefinePoints** (DIRECTION) | No Result | 절단 평면을 정의하는 점들을 지우고, 이를 재정의하기 위한 사용자 상호 작용을 시작한다. DIRECTION은 점들 사이의 선이 돌출될 방향을 지정한다. |
| **Colour** (REAL) | No Result | 절단 평면의 색상을 설정한다 (Real은 colour.code()여야 함). |
| **Translucency** (REAL) | No Result | 절단 평면의 투명도를 설정한다. 99 = 투명, 1 = 불투명. |
| **isValid** () | [[BOOLEAN\|BOOLEAN Object]] | 절단 평면 객체가 유효한지 확인한다. |
| **queryDbref** () | [[dbref\|dbref Object]] | 실제 데이터베이스 요소를 반환한다. |
| **queryShow** () | [[BOOLEAN\|BOOLEAN Object]] | 절단 평면의 표시 여부(show)를 가져온다. |
| **queryClip** () | [[BOOLEAN\|BOOLEAN Object]] | 절단 평면의 클리핑 값을 가져온다. |
| **queryType** () | [[STRING\|STRING Object]] | 절단 평면의 유형을 가져온다 (SPLA, FPLA, PPLA). |
| **queryColour** () | INTEGER | 절단 평면의 색상을 가져온다. |
| **queryTranslucency** () | INTEGER | 절단 평면의 투명도를 가져온다. |