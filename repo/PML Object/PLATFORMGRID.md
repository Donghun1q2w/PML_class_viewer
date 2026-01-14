---
tags: [PML2, E3D, 3D Geometry Objects, PLTFRM, Grid Pattern]
aliases: [PLATFORMGRID Object]
classification: 3D Geometry Objects
---

# [[PLATFORMGRID]]

## 개요
PLATFORMGRID 오브젝트는 PLTFRM 요소를 특정 그리드 패턴으로 채우는 데 사용된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **ASSIGN** (PLATFORMGRID) | NO RESULT | PLATFORMGRID 오브젝트의 내용을 현재 인스턴스로 복사한다. |
| **GRIDANGLE** () | [[REAL\|REAL Object]] | 사용된 그리드 각도 값을 반환한다. |
| **GRIDANGLE** (REAL) | NO RESULT | 그리드 각도 값을 설정한다. |
| **GRIDPOINT** (REAL1, REAL2) | NO RESULT | 주어진 인덱스 REAL1(X)과 REAL2(Y)로 식별되는 그리드 라인의 교차점 위치를 반환한다. |
| **GRIDPOSITION** () | [[position\|position Object]] | 그리드의 원점을 반환한다. |
| **GRIDXSPACINGS** () | [[ARRAY\|ARRAY Object]] | X축을 따른 그리드의 간격 패턴을 반환한다. |
| **GRIDXSPACINGS** (ARRAY) | NO RESULT | X축을 따른 그리드의 간격 패턴을 설정한다. |
| **GRIDXYPOSITION** () | XYPOSITION | 그리드 원점의 위치를 반환한다. |
| **GRIDXYPOSITION** (XYPOSITION) | NO RESULT | 그리드의 위치를 설정한다. |
| **GRIDXYSIZE** () | REAL ARRAY | 그리드를 포함하는 사각형의 크기를 반환한다. |
| **GRIDYSPACINGS** () | REAL ARRAY | Y축을 따른 그리드의 간격 패턴을 반환한다. |
| **GRIDYSPACINGS** (ARRAY) | NO RESULT | Y축을 따른 그리드의 간격 패턴을 설정한다. |
| **GROSSAREA** () | [[REAL\|REAL Object]] | 그리드의 총 면적을 반환한다. |
| **NETAREA** () | [[REAL\|REAL Object]] | 그리드의 순 면적을 반환한다. |
| **ORIENTATION** () | [[orientation\|orientation Object]] | 플랫폼의 방향(orientation)을 반환한다. |
| **ORIENTATION** (ORIENTATION) | NO RESULT | 주어진 값으로 플랫폼의 방향을 설정한다. |
| **PLANE** () | PLANE | 플랫폼 그리드의 평면(plane) 정의를 반환한다. 이는 PROFILE 오브젝트의 PLANE 메소드와 동일하다. |
| **PLATFORMGRID** () | PLATFORMGRID | PLATFORMGRID 오브젝트를 생성한다. |
| **PLATFORMGRID** (DBREF) | PLATFORMGRID | DBREF로부터 PLATFORMGRID를 생성한다. DBREF는 PLTGRD 또는 INTFRM 요소여야 한다. 외부 경계는 소유하고 있는 PLTFRM 라우팅 경로(RPATH)로부터 생성되며, 내부 경계는 PLOPEN 요소들로부터 생성된다. |
| **POSITION** () | [[position\|position Object]] | 플랫폼의 위치를 반환한다. |
| **POSITION** (POSITION) | NO RESULT | 그리드의 위치를 설정한다. |
| **XYSIZE** () | [[ARRAY\|ARRAY Object]] | 플랫폼 좌표계에서 그리드를 포함하는 사각형(한계)의 크기를 반환한다. |
| **ADDINNERBOUNDARY** (PROFILE) | NO RESULT | 그리드에 새로운 내부 경계를 추가한다. |
| **CLEARINNERBOUNDARY** () | NO RESULT | 모든 내부 경계를 삭제한다. |
| **INNERBOUNDARIES** () | PROFILE ARRAY | 내부 경계 프로파일들의 배열을 반환한다. |
| **INNERBOUNDARIES** (ARRAY) | NO RESULT | 내부 경계들을 교체한다. |
| **INNERBOUNDARY** (REAL) | PROFILE | 내부 경계의 프로파일을 반환한다. |
| **NUMBEROFINNERBOUNDARIES** () | [[REAL\|REAL Object]] | 그리드의 내부 경계 개수를 반환한다. |
| **OUTERBOUNDARY** () | PROFILE | 외부 경계 프로파일을 반환한다. |
| **CELLORIENTATION** (REAL1, REAL2) | [[orientation\|orientation Object]] | 주어진 인덱스로 식별되는 셀의 방향(orientation)을 반환한다. |
| **CELLPOSITION** (REAL1, REAL2) | [[position\|position Object]] | 주어진 인덱스로 식별되는 셀의 위치를 반환한다. |
| **CELLPROFILE** (REAL1, REAL2) | PROFILE | 주어진 인덱스로 식별되는 셀의 프로파일을 반환한다. |
| **CELLSIZE** (REAL1, REAL2) | REAL ARRAY | 주어진 인덱스로 식별되는 셀의 크기를 반환한다 (트리밍 전). |
| **CELLXYPOSITION** (REAL1, REAL2) | [[position\|position Object]] | 주어진 인덱스로 식별되는 셀의 위치를 반환한다. |
| **ISCELLTRIMMED** (REAL1, REAL2) | BOOL | 셀이 잘려진(trimmed) 경우 true를 반환한다. |
| **ISCELLUNTRIMMED** (REAL1, REAL2) | BOOL | 셀이 잘리지 않은(untrimmed) 경우 true를 반환한다. |
| **ISCELLWITHIN** (REAL1, REAL2) | BOOL | 셀이 그리드 내부에 있는 경우 true를 반환한다. |
| **LISTOFTRIMMEDCELLS** () | [[ARRAY\|ARRAY Object]] | 모든 잘려진(trimmed) 셀들의 인덱스를 반환한다. |
| **LISTOFTRIMMEDCELLS** (REAL) | [[ARRAY\|ARRAY Object]] | 면적이 주어진 REAL 값보다 큰 모든 잘려진 셀들의 인덱스를 반환한다. |
| **LISTOFUNTRIMMEDCELLS** () | [[ARRAY\|ARRAY Object]] | 모든 잘리지 않은(untrimmed) 셀들의 인덱스를 반환한다. |
| **TOTALNUMBEROFCELLS** () | [[REAL\|REAL Object]] | 그리드 내부의 셀 개수를 반환한다. |
| **TRIMMEDCELLSIZE** (REAL1, REAL2) | [[ARRAY\|ARRAY Object]] | 주어진 인덱스로 식별되는 셀을 포함하는 사각형의 크기를 반환한다. |
| **XGRIDLINES** () | [[ARRAY\|ARRAY Object]] | 그리드의 X 라인 배열을 반환한다. |
| **XGRIDLINES** (REAL) | [[ARRAY\|ARRAY Object]] | 주어진 인덱스의 그리드 X 라인 배열을 반환한다. |
| **YGRIDLINES** () | [[ARRAY\|ARRAY Object]] | 그리드의 Y 라인 배열을 반환한다. |
| **YGRIDLINES** (REAL) | [[ARRAY\|ARRAY Object]] | 주어진 인덱스의 그리드 Y 라인 배열을 반환한다. |