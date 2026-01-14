---
tags: [PML2, E3D, Forms, Menus, System]
aliases: [FMSYS Object]
classification: Forms and Menu Objects & Gadgets
---

# [[FMSYS]]

## 개요
FMSYS Object는 Forms and Menu Objects & Gadgets 분류에 속하는 객체이다. 이 객체에 포함된 메소드들은 원래의 객체를 수정하지 않는다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Checkrefs** | [[BOOLEAN\|BOOLEAN Object]] | 기본적으로 폼 정의 내의 모든 참조(references)는 폼이 표시될 때 확인된다. 성능 문제가 발생할 경우 이 확인 기능을 끌 수 있다. |
| **CurrentDocument**() | FORM | 이 메소드는 애플리케이션 프레임워크의 현재 Document를 FORM 객체로 반환한다. 현재 Document가 없으면 반환된 폼은 Unset 값을 가진다. |
| **DefaultFormat**() | FORMAT | 입력 텍스트 가젯에서 사용할 시스템 기본 포맷 객체를 쿼리한다. 정의된 것이 없으면 Unset 로컬 변수를 반환한다. 반환된 포맷 객체는 복사본이므로, 이를 변경해도 시스템 기본 포맷에는 영향을 주지 않는다. |
| **DefaultFormLayout**( ) | [[STRING\|STRING Object]] | 현재 기본 폼 레이아웃 모드를 쿼리한다. |
| **DocsAtMaxScreen**(BOOLEAN) | NO RESULT | 문서 폼(document forms)의 기본 배치 위치를 화면의 최대(오른쪽) 방향으로 설정한다. 와이드 스크린 및 듀얼 스크린 장치에 유용하다. |
| **FMINFO**() | ARRAY OF STRINGS | 모든 FMINFO 문자열의 배열을 반환한다. |
| **HelpFileAlias**() | [[STRING\|STRING Object]] | 현재 도움말 파일의 별칭(alias)을 반환한다. |
| **Interrupt**() | [[BOOLEAN\|BOOLEAN Object]] | 인터럽트 가젯이 선택된 경우 TRUE로 설정된다. |
| **LoadForm**(STRING formname) | FORM | 폼 정의를 강제로 로드하거나 이름으로 폼 객체에 대한 참조를 가져올 수 있게 한다. 폼이 존재하면 폼 객체에 대한 참조가 반환된다. 존재하지 않으면 정의를 강제로 로드하려고 시도한다. 실패하면 Unset 폼 참조가 반환된다. |
| **Main**() | FORM | 현재 메인 폼을 쿼리한다. |
| **OKCurfnView**(!viewtype is STRING) | [[BOOLEAN\|BOOLEAN Object]] | 지정된 뷰 타입의 그래픽 뷰가 표시되는지 쿼리한다. 지원되는 그래픽 뷰 타입은 ‘G2D’, ‘G3D’, ‘ANY’이며, 모든 뷰 서브타입이 암시된다. |
| **OKCurfnView**(!viewtype is STRING, subtype is STRING ) | [[BOOLEAN\|BOOLEAN Object]] | 지정된 뷰 타입과 서브타입의 그래픽 뷰가 표시되는지 쿼리한다. 지원되는 그래픽 뷰 타입은 ‘G2D’, ‘G3D’, ‘ANY’이다. 지원되는 뷰 서브타입은 ‘ANY’ 및 G2D의 경우 ‘NORMAL’ (Draft), ‘PLOT’, ‘ISOSPOOL’, G3D의 경우 ‘NORMAL’ (Design)이다. |
| **Progress**( ) | [[REAL\|REAL Object]] | 프로그레스 바에 표시된 현재 정수 값을 퍼센트(0~100 범위)로 가져온다. 0은 바가 보이지 않음을 의미한다. |
| **Refresh**() | NO RESULT | 모든 VIEW 가젯을 새로 고침(Refresh)한다. |
| **SetDefaultFormat**(!!fmt is FORMAT) | NO RESULT | 특정 포맷이 정의되지 않은 입력 텍스트 필드에서 사용할 기본 전역 포맷 객체를 제공한다. 한 번만 호출할 수 있으며, 사용자가 변경할 수 없다. !!fmt는 전역 변수여야 한다. |
| **SetDefaultFormLayout** ( STRING ) | NONE | 기본 폼 레이아웃 모드를 'VARCHARS' 또는 'FIXCHARS'로 설정한다. |
| **SetHelpFileAlias** (alias is string) | NONE | 별칭(alias)으로부터 애플리케이션 도움말 파일을 설정(establish)한다. |
| **SetInterrupt**(GADGET) | NO RESULT | 매크로 또는 함수 처리를 중단(interrupt)할 가젯을 설정한다. |
| **SetMain**(FORM) | FORM | 애플리케이션의 메인 폼을 설정한다. |
| **SetProgress**( !percent) | NO RESULT | 프로그레스 바에 표시될 정수 값을 퍼센트로 설정한다. 값은 0에서 100 사이의 범위로 강제된다. 결과 값이 0이면 바가 보이지 않게 된다. |
| **Splashscreen**(BOOLEAN) | NO RESULT | 비정상 종료 후 스플래시 화면의 표시를 제거한다. |