---
tags: [PML2, E3D, Gadget, Menu, Form]
aliases: [BAR Object, Bar Menu]
classification: Forms and Menu Objects & Gadgets
---

# [[BAR]]

## 개요
BAR 명령은 폼 정의(form definition) 내에서 바 메뉴(bar menu)를 생성한다. 바(bar)에 메뉴 필드를 생성하는 권장 방법은 bar의 Add() 메소드를 사용하는 것이다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Add** (STRING dText, STRING enu) | NO RESULT | 풀다운 메뉴(pulldown menu)로 지정된 메뉴를 표시할 수 있는 바 메뉴(barmenu) 필드를 추가한다. 풀다운 메뉴의 이름은 `menu`에 지정하고, 필드의 DTEXT는 `dText`로 지정한다. |
| **Clear** () | NO RESULT | 모든 바 메뉴 필드를 제거한다. 이 메소드의 사용은 더 이상 권장되지 않는다(deprecated). |
| **Clear** (STRING dText) | NO RESULT | `dText`를 가진 필드를 포함하여 그 이후의 모든 바 메뉴 필드를 제거한다. 이 메소드의 사용은 더 이상 권장되지 않는다(deprecated). |
| **FieldProperty** (STRING field, STRING property) | [[BOOLEAN\|BOOLEAN Object]] | `field`로 명명된 메뉴 필드에 대해 `property`로 명명된 속성의 값을 가져온다. 속성에 허용되는 값은 'ACTIVE' 또는 'VISIBLE'이다. |
| **FullName** () | [[STRING\|STRING Object]] | 가젯의 전체 이름(예: '!!Form.bar')을 가져온다. |
| **InsertAfter** (STRING field, STRING dText, STRING menu) | NO RESULT | `field`로 식별된 필드 바로 뒤에 새로운 바 메뉴 필드를 삽입한다. 메뉴의 이름은 `menu`에, 새 필드의 DTEXT는 `dText`에 지정한다. |
| **InsertBefore** (STRING field, STRING dText, STRING menu) | NO RESULT | `field`로 식별된 필드 바로 앞에 새로운 바 메뉴 필드를 삽입한다. 메뉴의 이름은 `menu`에, 메뉴의 DTEXT는 `dText`에 지정한다. |
| **Name** () | [[STRING\|STRING Object]] | 가젯의 이름(즉, 'bar')을 가져온다. |
| **Owner** () | FORM | 소유하고 있는 폼(form)을 가져온다. |
| **SetActive** (STRING dText, BOOLEAN state) | NO RESULT | DTEXT가 `dText`인 메뉴 필드를 비활성화/활성화한다. 이 메소드의 사용은 더 이상 권장되지 않는다(deprecated). |
| **SetFieldProperty** (STRING menu, STRING property, BOOLEAN state) | NO RESULT | `menu`로 명명된 메뉴에 대해 `property`로 명명된 속성의 값을 `state` 값으로 설정한다. 속성에 허용되는 값은 'ACTIVE' 또는 'VISIBLE'이다. |
| **Shown** () | [[BOOLEAN\|BOOLEAN Object]] | 표시 상태(shown status)를 가져온다. |
| **Type** () | [[STRING\|STRING Object]] | GADGET 타입을 문자열(STRING)로 가져온다. |

## 커맨드 (Commands)
```pml
bar
!this.bar.add ( 'Choose', 'Menu1')
!this.bar.add ( ' window', 'Window' )
!this.bar.add ( 'help', 'Help' )
```

## 노트 (Notes)
- 'Help'이라는 두 가지 특별한 메뉴 이름을 사용하면 온라인 도움말을 호출하는 시스템 도움말 메뉴가 추가되고, 'Window'를 사용하면 표시된 모든 창을 나열하는 시스템 창 메뉴가 추가된다.