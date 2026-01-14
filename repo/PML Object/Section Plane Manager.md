---
tags: [PML2, E3D, Draft, Graphics, 3D View, Section Plane]
aliases: [Section Plane Manager Object]
classification: Graphical Object
---

# [[Section Plane Manager]]

## 개요
Graphical Section Plane Manager Object는 Draft 모듈의 3D View 내에서 Section Plane(단면 평면)을 조회하고 수정하기 위한 인터페이스를 제공한다. 3D View에 추가된 모든 PML SectionPlane Object들의 리스트를 유지 관리한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **SectionPlaneManager** () | constructor | Section Plane Manager Object를 생성한다. |
| **initialise** (BOOLEAN) | No Result | True인 경우 Section plane 모드를 초기화하고, False인 경우 Section Plane 모드를 해제한다. |
| **add** (DBREF) | No Result | DBREF가 View인 경우 2D View(Draft VIEW 요소)의 모든 Section Plane을 3D View에 추가한다.\u003cbr\u003eDBREF가 PLLB인 경우 2D Library의 모든 Section Plane(SPLA, PPLA, FPLA 포함)을 3D View에 추가한다.\u003cbr\u003eDBREF가 SPLA, PPLA, 또는 FPLA인 경우 해당 요소를 3D View에 추가한다.\u003cbr\u003e추가된 각 Section Plane에 대해 SECTIONPLANE Object가 생성되어 리스트에 추가된다. |
| **add** (SECTIONPLANE) | No Result | SECTIONPLANE Object를 3D View에 추가한다. |
| **add** (STRING) | No Result | 주어진 이름을 가진 요소로부터 SECTIONPLANE Object를 생성하고 3D View에 추가한다. |
| **remove** (DBREF) | No Result | DBREF가 SPLA, PPLA, 또는 FPLA인 경우 3D View에서 제거한다. 대응하는 SECTIONPLANE Object가 리스트에 있다면 제거된다. |
| **remove** (SECTIONPLANE) | No Result | 3D View와 리스트에서 SECTIONPLANE Object를 제거한다. |
| **clear** () | No Result | 3D View에서 모든 Section Plane을 지운다. |
| **highlight** (DBREF) | No Result | 해당 DBREF를 가진 Section Plane을 일시적으로 강조(Highlight)한다. |
| **redraw** (DBREF) | No Result | 3D View의 모든 Plane을 다시 그린다. Plane은 양방향으로 무한하지만 현재 Drawlist의 가장자리에 맞춰 잘린(clipped) 형태로 그려진다. 따라서 Plane이 이동하거나 Drawlist가 변경되면 다시 그려야 할 수 있다. DBREF는 VIEW 요소의 참조이다. |
| **clip** (BOOLEAN) | No Result | 3D View에 표시된 모든 Plane을 사용하여 3D View 내의 3D 모델을 클립(Clip)/언클립(Unclip)한다. SPLA 아이템은 클립되지 않는다. |
| **show** (BOOLEAN) | No Result | 3D View의 모든 Plane을 표시하거나 숨긴다. |
| **showClipping** (BOOLEAN) | No Result | 클립될 각 Section Plane의 측면을 표시하거나 숨긴다. |
| **colour** (REAL) | No Result | 모든 Section Plane의 색상을 설정한다 (Real 값은 colour.code()여야 함). |
| **translucency** (REAL) | No Result | 모든 Section Plane의 투명도를 설정한다. 99는 투명, 1은 불투명이다. |
| **createPoints** (STRING1, STRING2, DIRECTION) | No Result | 이름이 STRING2인 PLLB 내에 STRING1 이름을 가진 SPLA를 생성하고, 주어진 DIRECTION으로 돌출시킨다. |
| **endCreatePoints** | No Result | SPLA를 위한 포인트 수집을 완료한다. |
| **query** () | ARRAY of SECTIONPLANEs | 3D View에 있는 모든 Section Plane을 가져온다. |
| **querySelected** () | [[dbref\|dbref Object]] | 선택된 Section Plane의 DBREF를 반환한다. |
| **createSpla** (name, library name, first point, second point, extrusion direction) | SECTIONPLANE | 특정 라이브러리에 지정된 이름으로 새로운 SPLA 요소를 생성한다. 첫 번째와 두 번째 포인트는 처음 두 개의 WPOS 요소 위치를 나타낸다(시스템에 의해 기본 이름으로 자동 생성됨). 돌출 방향(Extrusion direction)도 설정해야 한다. 새로운 SPLA는 3D View에 그려진다. |
| **createFpla** (name, library name, point, normal direction) | SECTIONPLANE | 특정 라이브러리에 지정된 이름으로 새로운 FPLA 요소를 생성한다. 위치(Position)와 법선 방향(Normal direction)을 설정해야 한다. 새로운 FPLA는 3D View에 그려진다. |
| **createPpla** (name, library name, point) | SECTIONPLANE | 특정 라이브러리에 지정된 이름으로 새로운 PPLA 요소를 생성한다. 위치(Position)를 설정해야 한다. 새로운 PPLA는 3D View에 그려진다. |