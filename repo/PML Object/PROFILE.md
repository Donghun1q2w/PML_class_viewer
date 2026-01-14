---
tags: [PML2, E3D, Geometry, 3D, PROFILE]
aliases: [PROFILE Object]
classification: 3D Geometry Objects
---

# [[PROFILE]]

## 개요
LOOP, PLOO, PALJ 또는 SPINE으로부터 PROFILE 객체를 생성한다. POGO, BOUN, DRAW로부터는 근사적으로 생성된다. 3D 선형 형상(SPINE, BOUN, DRAW, PALJ)은 단일 평면에 있어야 한다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **Position** | [[position\|position Object]] | 프로파일의 원점 (Origin of profile) |
| **Orientation** | [[orientation\|orientation Object]] | 프로파일 평면의 방향 (Orientation of profile plane) |
| **Pointer** | POINTER | 프로파일의 정의 (Definition of profile) |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Profile** (POSITION, ORIENTATION, ARRAY) | PROFILE | 프로파일 객체를 생성한다. 입력 ARRAY는 LINEs, ARCs, POSITIONs의 배열이다. 다른 배열 멤버 타입은 무시된다. 배열 멤버는 올바르게 초기화되어야 하며, 그렇지 않으면 무시된다. |
| **Profile** (DBREF) | PROFILE | LOOP, PLOO, PALJ 또는 SPINE으로부터 프로파일 객체를 생성한다. POGO, BOUN, DRAW로부터는 근사적으로 생성된다. 3D 선형 형상(SPINE, BOUN, DRAW, PALJ)은 단일 평면에 있어야 한다. 그렇지 않으면 요소의 처음 몇 점에 의해 정의된 평면에 투영된다. |
| **Profile** (DBREF1, DBREF2) | PROFILE | DBREF1에 있는 SPRO 또는 SLOO로부터 프로파일 객체를 생성한다. DBREF2는 카탈로그 프리미티브를 참조하는 설계 요소(design element)로, 매개변수를 제공한다. |
| **Profile** (PROFILE) | PROFILE | 주어진 프로파일의 복사본인 프로파일 객체를 생성한다. |
| **Plane** () | PLANE | 프로파일의 PLANE 정의를 반환한다. 이는 LINEARGRID 객체의 PLANE 메소드와 동일하다. |
| **IsClosed** () | [[BOOLEAN\|BOOLEAN Object]] | 닫혀있으면(closed) TRUE를 반환한다. |
| **IsValidClosed** () | [[BOOLEAN\|BOOLEAN Object]] | 프로파일이 유효하고 GML을 사용하여 올바르게 그려질 수 있는 경우(예: 자체 교차하는 모서리가 없음) TRUE를 반환한다. |
| **Sense** () | [[BOOLEAN\|BOOLEAN Object]] | 반시계 방향(평면 상에서)인 경우 TRUE를 반환한다. 프로파일이 닫혀있지 않으면 오류를 반환한다. |
| **Area** () | [[REAL\|REAL Object]] | 프로파일의 내부 면적을 반환한다. 프로파일이 닫혀있지 않으면 오류를 반환한다. |
| **Length** () | [[REAL\|REAL Object]] | 프로파일의 전체 길이를 반환한다. |
| **IsCircle** () | [[BOOLEAN\|BOOLEAN Object]] | 프로파일이 완전한 원인 경우 TRUE를 반환한다. |
| **IsFillet** (REAL) | [[BOOLEAN\|BOOLEAN Object]] | REAL 인수로 지정된 모서리가 필렛(fillet)인 경우 TRUE를 반환한다. 필렛은 인접한 모서리(선 또는 더 큰 반경의 호)와 접선적으로 연속되는 유의미한 각도를 가진 호(arc)여야 한다. |
| **edges** () | [[ARRAY\|ARRAY Object]] | 프로파일을 정의하는 선(lines)과 호(arcs)의 배열을 반환한다. 선과 호의 방향과 감각(sense)이 중요하다. 프로파일이 완전한 원인 경우, 프로파일의 구성과 관계없이 단일 전체 원 호가 반환된다. |
| **numberEdges** () | [[REAL\|REAL Object]] | 프로파일 내의 모서리 수를 반환한다 (= 꼭짓점 수 - 1). |
| **edge** (REAL) | LINE/ARC | edges 배열의 전달된 인덱스에 있는 프로파일 요소를 반환한다. |
| **dbWrite** (DBREF) | PROFILE | DBREF를 프로파일의 내용으로 채운다. 형상이 이미 존재하는 경우 프로파일 형상으로 대체된다. 저장되는 형상은 데이터베이스 요소에 적합한 것이다. DBREF는 LOOP, PLOO, PALJ, SPINE, BOUN, DRAW, POGO 중 하나여야 한다. 수정되지 않은 상태로 반환된다. LOOP 또는 PLOO의 소유자는 프로파일에 맞게 재배치된다. 다른 형상은 소유자 또는 위치가 지정된 조상(ancestor)의 참조 프레임 내에서 올바르게 위치된다. 카탈로그 형상의 채우기(Population)는 지원되지 않는다. |
| **draw** (REAL1, REAL2, REAL3) | PROFILE | 프로파일을 보조(aid) 선과 호의 집합으로 그린다. REAL1은 그릴 세그먼트 번호이다. REAL2는 세그먼트의 스타일을 설정한다. REAL3는 세그먼트의 색상을 설정한다. 그려진 그래픽은 AID 형상 함수를 사용하여 쿼리 및 조작할 수 있다. |
| **mirror** (LINE) | PROFILE | 경계 평면에 매핑될 때, 전달된 라인에 대해 경계 정의를 미러링한다. |
| **translate** (REAL1, REAL2) | PROFILE | 경계 평면의 XY에서 경계 정의를 REAL1의 x와 REAL2의 y만큼 이동(offset)한다. |
| **rotate** (REAL, POSITION) | PROFILE | 주어진 각도만큼 POSITION을 중심으로 경계 정의를 회전한다. 각도는 경계 평면의 Z축에 대해 반시계 방향이다. |
| **close** () | PROFILE | 추가적인 모서리로 프로파일을 닫는다(필요한 경우). 끝점이 허용 오차 내에 있으면 끝점이 조정된다. |
| **reverse** () | PROFILE | 프로파일의 감각(sense)과 모서리의 순서를 반전시킨다. |
| **mergearcs** (REAL1, REAL2) | PROFILE | 허용 오차 REAL2에 따라 최대 호 각도 REAL1 도(degrees)까지의 동심 인접 호를 하나로 병합한다. Mergearcs()는 프로파일 내의 동심 역추적(back tracks)도 제거한다. |
| **mergearcs** () | PROFILE | 동심 인접 호를 하나로 병합한다. |
| **mergelines** (REAL) | PROFILE | 제공된 허용 오차에 따라 동일 선상의 인접한 선을 하나로 병합한다. Mergelines()는 프로파일 내의 동일 선상 역추적(back tracks)도 제거한다. |
| **mergelines** () | PROFILE | 동일 선상의 인접한 선을 하나로 병합한다. |
| **mergepoints** (REAL) | PROFILE | 제공된 허용 오차에 따라 일치하는 연속 점을 제거한다. |
| **mergepoints** () | PROFILE | 일치하는 연속 점을 제거한다. |
| **polyline** (REAL) | PROFILE | 제공된 허용 오차에 따라 호(arcs)를 현(chordal) 근사치로 대체한다. |
| **polyline** () | PROFILE | 호(arcs)를 현(chordal) 근사치로 대체한다. |
| **projectArcs** (REAL) | PROFILE | 정의에서 모든 호를 제거하고 직선 모서리만 남긴다. 제공된 인수보다 작은 각도의 호는 무시된다. 제거된 호는 호의 극(polar) 위치에서 만나는 투영된 접선으로 대체된다. 180도에 가까운 각도를 가진 호는 반으로 분할된다. |
| **Near** (POSITION) | [[position\|position Object]] | 프로파일 평면에 투영된 주어진 위치에 대해, 프로파일 상의 가장 가까운 위치를 반환한다. |
| **Near** (REAL, POSITION) | [[position\|position Object]] | REAL 인수는 프로파일 내의 모서리에 대한 인덱스이다. 제공된 POSITION에 대해 이 모서리 상의 가장 가까운 점을 반환한다. 이는 .near(POSITION)과 같지만 단일 모서리로 제한된다. |
| **NearEdges** (POSITION) | [[ARRAY\|ARRAY Object]] | 주어진 POSITION에 가장 가까운 모서리들의 모서리 인덱스 배열을 반환한다. 반환된 모서리는 프로파일 내의 어느 것이든 될 수 있다. 가장 가까운 점이 꼭짓점인 경우 모서리는 연속적이다. |
| **IsWithin** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 위치가 프로파일 평면에 매핑될 때 프로파일 내부에 있으면 TRUE를 반환한다. 프로파일은 닫혀있어야 한다. |
| **IsWithout** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 위치가 프로파일 평면에 매핑될 때 프로파일 완전히 외부에 있으면 TRUE를 반환한다. 프로파일은 닫혀있어야 한다. |
| **OnProfile** (POSITION) | [[BOOLEAN\|BOOLEAN Object]] | 위치(프로파일 평면에 매핑됨)가 프로파일 형상 위에 있으면 TRUE를 반환한다. |
| **IsWithin** (PROFILE) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 프로파일이 객체 프로파일 내에 완전히 포함되면 True이다. 두 프로파일 모두 닫혀있어야 한다. |
| **IsWithout** (PROFILE) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 프로파일이 객체 프로파일 외부에 완전히 있으면 True이다. 두 프로파일 모두 닫혀있어야 한다. |
| **IsIntersecting** (PROFILE) | [[BOOLEAN\|BOOLEAN Object]] | 제공된 프로파일이 객체 프로파일과 교차하면 True이다. 두 프로파일 모두 닫혀있어야 한다. |
| **intersections** (LINE) | ARRAY OF POINTS | 선(또는 프로파일 평면에 투영된 선)이 프로파일과 교차하는 위치인 점들의 배열을 반환한다. 확장된 무한 선 상의 모든 점이 반환된다. |
| **intersections** (ARC) | ARRAY OF POINTS | 호(또는 프로파일 평면에 투영된 호)가 프로파일과 교차하는 위치인 점들의 배열을 반환한다. 호의 평면은 프로파일의 평면과 평행해야 하며, 그렇지 않으면 오류가 발생한다. 점들은 호의 원 상의 어디에나 있을 수 있다(시작과 끝 사이로 제한되지 않음). |
| **intersections** (PROFILE) | ARRAY OF POINTS | 두 프로파일이 교차하는 위치인 점들의 배열을 반환한다. 두 프로파일은 서로 평행(또는 반-평행)해야 한다. |
| **intersect** (PROFILE) | ARRAY OF PROFILES | 결과 교차 프로파일의 배열을 반환한다. |
| **union** (PROFILE) | ARRAY OF PROFILES | 두 프로파일의 합집합을 반환한다. 구멍(Holes)은 별도의 프로파일(반대 방향)로 반환된다. |
| **difference** (PROFILE) | ARRAY OF PROFILES | 프로파일 정의에 대해 전달된 프로파일의 차집합(difference)을 반환한다. |
| **split** (LINE) | ARRAY OF PROFILES | 전달된 선을 프로파일에 투영하고 그 선을 기준으로 분할하여 생성된 결과 프로파일들을 반환한다. |
| **split** (PLANE, BOOLEAN) | ARRAY OF PROFILES | 전달된 평면과 프로파일 평면의 교차선에서 프로파일을 분할하여 생성된 결과 경계들을 반환한다. 측면(side)은 제공된 BOOLEAN에 의해 지정된다. TRUE이면 전달된 평면의 법선 방향에 있는 프로파일만 생성되고, FALSE이면 반-법선 방향의 프로파일만 생성된다. |