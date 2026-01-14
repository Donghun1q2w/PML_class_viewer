---
tags: [PML2, E3D, MultiDisciplineRouteManager, mdrRoutePoint]
aliases: [mdrRoutePoint Object]
classification: PDMS Objects
---

# [[mdrRoutePoint]]

## 개요
매뉴얼에 별도의 개요가 기술되어 있지 않으나, Multi Discipline Route Manager 섹션에 정의된 라우트 포인트 객체로, 위치, 반경, 외부 형상 등의 속성을 관리하는 메소드들을 제공합니다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **OwningDbBranch** | [[dbref\|dbref Object]] | 이 라우트 포인트의 소유 브랜치 요소를 반환한다. |
| **OwningRoute** | mdrRoute | 소유하고 있는 mdrRoute를 반환한다. |
| **IsEqual** (mdrRoutePoint) | [[BOOLEAN\|BOOLEAN Object]] | 객체들이 동일한지 확인한다. 먼저 기초가 되는 DB 요소로 비교하고, 그렇지 않으면 Position On을 사용한다. |
| **ExpandToRoute** | mdrRoute | 외부 형상을 mdrRoute 객체로 확장한다. |
| **IsExternalGeometry** | [[BOOLEAN\|BOOLEAN Object]] | 외부 형상 객체인 경우 True를 반환한다. |
| **EndingRoutePoint** (mdrRoutePoint) | NO RESULT | 외부 형상 종료 라우트 포인트를 설정한다. (외부 형상 타입 라우트 포인트인 경우에만 유효) |
| **EndingRoutePoint** | mdrRoutePoint | 외부 형상 종료 라우트 포인트를 가져온다. (외부 형상 타입 라우트 포인트인 경우에만 유효) |
| **StartingRoutePoint** (mdrRoutePoint) | NO RESULT | 외부 형상 시작 라우트 포인트를 설정한다. (외부 형상 타입 라우트 포인트인 경우에만 유효) |
| **StartingRoutePoint** | mdrRoutePoint | 외부 형상 시작 라우트 포인트를 가져온다. (외부 형상 타입 라우트 포인트인 경우에만 유효) |
| **Position** | [[position\|position Object]] | 월드 좌표계에서 라우트 포인트의 위치를 가져온다. (외부 형상 타입이 아닌 경우에만 유효) |
| **Position** (Position) | NO RESULT | 월드 좌표계에서 라우트 포인트의 위치를 설정한다. (외부 형상 타입이 아닌 경우에만 유효) |
| **Radius** | [[REAL\|REAL Object]] | 라우트 포인트의 필렛(fillet) 반경을 가져온다. |
| **Radius** (Real) | NO RESULT | 라우트 포인트의 필렛(fillet) 반경을 설정한다. (외부 형상 타입이 아닌 경우에만 유효) |
| **Clone** | mdrRoutePoint | 복제된 객체를 반환한다. (기초가 되는 DB 요소와 이름을 제외한 모든 속성을 복제) |
| **Name** | [[STRING\|STRING Object]] | 명명된 라우트 포인트의 이름을 가져온다. |
| **Is That** (String type) | [[BOOLEAN\|BOOLEAN Object]] | 명명된 타입이 인수로 전달된 것과 일치하면 True를 반환한다. |
| **Type** | [[STRING\|STRING Object]] | 라우트 포인트 객체의 타입을 가져온다. |
| **Type** (String type) | NO RESULT | 라우트 포인트 객체의 타입을 설정한다. |
| **DbElement** | [[dbref\|dbref Object]] | 기초가 되는 DB 요소를 가져온다. |
| **IsEnabled** | [[BOOLEAN\|BOOLEAN Object]] | 요소가 활성화되었는지 확인한다. |
| **IsNamed** | [[BOOLEAN\|BOOLEAN Object]] | 요소가 명명되었는지 확인한다. |
| **IsOn** | [[BOOLEAN\|BOOLEAN Object]] | 라우트 포인트가 동일한 위치에 있으면 True를 반환한다. |
| **DbElement** (DBREF) | NO RESULT | 소유된 DB 요소를 설정한다. |
| **Enable** (Boolean enabled) | NO RESULT | 라우트 포인트를 활성화하거나 비활성화한다. |