---
tags: [PML2, E3D, ViewFinder, Draft, 3D View, Frame, Graphics]
aliases: [ViewFinder Object]
classification: PDMS Objects
---

# [[ViewFinder]]

## 개요
Draft PML 사용자가 2D 뷰의 뷰 프레임을 나타내는 프레임을 3D 뷰에 생성할 수 있게 한다. 그려진 프레임은 이동 및 회전이 가능하며, 3D 뷰에서 프레임을 조작함으로써 사용자는 현재 도면의 뷰 매개변수를 수정할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **viewFinder** (DBREF) | ViewFinder | Draft View의 매개변수를 기반으로 viewfinder 객체를 생성한다. 입력 인자는 유효한 View의 dbref여야 한다. |
| **view** (DBREF) | NO RESULT | DBREF를 사용하여 연관된 View 객체를 설정하며, 이는 유효한 view여야 한다. |
| **redraw** () | No Result | View 매개변수의 현재 상태를 사용하여 상자를 다시 그린다. |
| **update3d** () | No Result | 2D 뷰로부터 프레임과 3D 모델 뷰를 재생성한다. |
| **colour** (REAL) | No Result | 지정된 PDMS 색상 번호로 색상을 변경한다. |
| **translucency** (BOOLEAN) | No Result | 반투명도를 켜거나 끈다. |
| **align** () | No Result | viewfinder 프레임을 3D 뷰 방향과 정렬한다. |
| **lock** (BOOLEAN) | No Result | 프레임이 이동되지 않도록 잠그거나 잠금을 해제한다. |
| **dynamic** (BOOLEAN) | No Result | 참(True)이면, 프레임이 이동될 때마다 설계 업데이트(update design)가 자동으로 발생한다. |
| **hide** () | No Result | 프레임을 보이지 않게 만든다. |
| **show** () | No Result | 프레임을 보이게 만든다. 또한 프레임이 포함되도록 클리핑 평면을 확장한다. |
| **valid** () | [[BOOLEAN\|BOOLEAN Object]] | viewfinder가 유효한지 확인한다. 유효한 View로 생성된 경우 참(True), 그렇지 않으면 거짓(False)이다. |
| **view** () | [[dbref\|dbref Object]] | 연관된 view 객체의 dbref를 반환한다. |
| **position** () | [[position\|position Object]] | viewfinder 프레임의 중심 위치를 반환한다. |
| **direction** () | [[Direction\|Direction Object]] | viewfinder와 연관된 View의 방향을 반환한다. |
| **size** () | ARRAY of REAL | viewfinder 프레임의 크기를 반환한다 (Xnnn Ynnn 형식). |
| **dynamic** () | [[BOOLEAN\|BOOLEAN Object]] | 동적 모드(dynamic mode)인 경우 참(True)을 반환한다. |