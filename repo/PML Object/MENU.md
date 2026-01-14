---
tags: [PML2, E3D, GUI, Menu, Form]
aliases: [MENU Object]
classification: Forms and Menu Objects & Gadgets
---

# [[MENU Object]]

## 개요
MENU 객체는 FORM 객체가 소유하며, 폼 설정(setup) 모드 내에서 생성할 수 있습니다. 또한 기존 폼에 새로운 메뉴를 추가하는 것도 가능하며, 이는 주로 상황에 맞는(context sensitive) 팝업 메뉴로 사용됩니다.

## 멤버 (Members)

| Name                | Type   | Purpose                                                                                 |
| :------------------ | :----- | :-------------------------------------------------------------------------------------- |
| **Callback**        | [[STRING\|STRING Object]] | 메뉴의 콜백(callback)을 설정하거나 가져옵니다.                                                          |
| **PickedField**     | [[STRING\|STRING Object]] | 마지막으로 선택된 메뉴 필드의 DTEXT를 반환합니다. (이 멤버의 사용은 현재 권장되지 않습니다. 대신 PickedFieldName 속성을 사용하십시오.) |
| **PickedFieldName** | [[STRING\|STRING Object]] | 마지막으로 선택된 TOGGLE 또는 CALLBACK 필드의 필드 이름을 반환합니다.                                          |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Add**('SEPARATOR', {STRING fieldName}) | NO RESULT | SEPARATOR 필드를 추가합니다. 선택적 인자인 fieldName이 존재하면 메뉴 내에서 고유한 필드 이름을 나타냅니다. |
| **Add**('CALLBACK', STRING Dtext, STRING callback, {STRING fieldName}) | NO RESULT | Dtext를 가진 CALLBACK 필드를 추가합니다. Dtext는 멀티바이트 문자를 포함할 수 있으나 NULL이나 공백일 수 없습니다. callback 인자는 콜백 명령을 제공합니다. 선택적 인자인 fieldName이 존재하면 메뉴 내에서 고유한 필드 이름을 나타냅니다. |
| **Add**('FORM', STRING Dtext, STRING formName, {STRING fieldName}) | NO RESULT | Dtext를 가진 FORM 표시 필드를 추가합니다. formName 인자는 표시될 폼의 이름을 제공하며, NULL일 수 있으나 공백일 수 없습니다. 선택적 인자인 fieldName이 존재하면 메뉴 내에서 고유한 필드 이름을 나타냅니다. |
| **Add**('MENU', STRING DText, STRING menuName, {STRING fieldName}) | NO RESULT | Dtext를 가진 MENU(pullright) 필드를 추가합니다. menuName은 pullright 메뉴 이름을 제공하며, NULL일 수 있으나 공백일 수 없습니다. 선택적 인자인 fieldName이 존재하면 메뉴 내에서 고유한 필드 이름을 나타냅니다. |
| **Add**('TOGGLE', STRING Dtext, STRING callback, {STRING fieldName}) | NO RESULT | Dtext를 가진 TOGGLE 필드를 추가합니다. callback 인자는 콜백 명령을 제공하며, 이는 반드시 open PML 함수여야 합니다. 선택적 인자인 fieldName이 존재하면 메뉴 내에서 고유한 필드 이름을 나타냅니다. |
| **Clear**() | NO RESULT | 메뉴에서 모든 메뉴 필드를 제거합니다. (이 메소드의 사용은 권장되지 않습니다.) |
| **Clear**(STRING Dtext) | NO RESULT | Dtext와 일치하는 필드부터 그 이후의 메뉴 필드들을 제거합니다. (이 메소드의 사용은 권장되지 않습니다.) |
| **FieldProperty**(STRING menuField, STRING property) | [[BOOLEAN\|BOOLEAN Object]] | menuField로 명명된 메뉴 필드에 대해 property로 명명된 속성의 값을 가져옵니다. property에 허용되는 값은 'ACTIVE', 'VISIBLE', 'SELECTED'입니다. |
| **FullName**() | [[STRING\|STRING Object]] | 메뉴 객체의 전체 이름을 반환합니다. 예: '!!Form.Menu'. |
| **InsertAfter**(STRING menuField, 'CALLBACK', STRING Dtext, STRING callback, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 뒤에 CALLBACK 필드를 삽입합니다. |
| **InsertAfter**(STRING menuField, 'FORM', STRING Dtext, STRING formName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 뒤에 FORM 표시 필드를 삽입합니다. |
| **InsertAfter**(STRING menuField, 'MENU', STRING Dtext, STRING menuName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 뒤에 MENU(pullright) 필드를 삽입합니다. |
| **InsertAfter**(STRING menuField, 'TOGGLE', STRING Dtext, STRING menuName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 뒤에 TOGGLE 필드를 추가합니다. |
| **InsertAfter**(STRING menuField, 'SEPARATOR', {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 뒤에 SEPARATOR 필드를 추가합니다. |
| **InsertBefore**(STRING menuField, 'CALLBACK', STRING Dtext, STRING callback, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 앞에 CALLBACK 필드를 삽입합니다. |
| **InsertBefore**(STRING menuField, 'FORM', STRING Dtext, STRING formName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 앞에 FORM 표시 필드를 삽입합니다. |
| **InsertBefore**(STRING menuField, 'MENU', STRING Dtext, STRING menuName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 앞에 MENU(pullright) 필드를 삽입합니다. |
| **InsertBefore**(STRING menuField, 'TOGGLE', STRING Dtext, STRING menuName, {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 앞에 TOGGLE 필드를 추가합니다. |
| **InsertBefore**(STRING menField, 'SEPARATOR', {STRING fieldName}) | NO RESULT | menuField로 식별되는 메뉴 필드 바로 앞에 SEPARATOR 필드를 추가합니다. |
| **Name**() | [[STRING\|STRING Object]] | 메뉴 객체의 단순 이름을 반환합니다. 예: 'Menu'. |
| **Owner**() | FORM | 소유하고 있는 폼(form)에 대한 참조를 반환합니다. |
| **PopupGadget**() | GADGET | 메뉴를 팝업시킨 가젯의 이름을 반환합니다. 가젯에 의해 팝업되지 않은 경우 값은 unset 상태입니다. |
| **Refresh**() | NO RESULT | 가젯의 표시를 새로 고칩니다. |
| **Select**(STRING Dtext, BOOLEAN status) | NO RESULT | Dtext로 식별되는 TOGGLE 필드의 선택 상태를 status 값으로 설정합니다. (이 메소드의 사용은 권장되지 않습니다.) |
| **Selected**(STRING Dtext) | [[BOOLEAN\|BOOLEAN Object]] | Dtext로 식별되는 TOGGLE 필드의 선택 상태를 가져옵니다. (이 메소드의 사용은 권장되지 않습니다.) |
| **SetActive**(STRING Dtext, BOOLEAN active) | NO RESULT | Dtext로 식별되는 메뉴 필드의 active 상태를 설정합니다. (이 메소드의 사용은 권장되지 않습니다.) |
| **SetFieldProperty**(STRING menuField, STRING property, BOOLEAN value) | NO RESULT | menuField로 식별되는 메뉴 필드에 대해 property의 값을 value로 설정합니다. property에 허용되는 값은 'ACTIVE', 'VISIBLE', 'SELECTED'입니다. |

## 커맨드 (Commands)
`MENU` 명령은 폼 설정 모드(form setup mode) 내에서 사용될 수 있습니다. 또는 `Add` 명령들을 뒤따라 사용하고 `EXIT` 명령으로 종료할 수 있습니다.

```
\u003e-- MENU -- gname -+- POPUP --. .--------\u003c-------.
                   +- MAIN --| /                 |
                   '----------'-+- NL -+- \u003cfmenu\u003e -|
                                +- PML -----*
                                +- EXIT ----.
                                '-----------'--\u003e
```

```
.-----\u003c-----.
/             |
fmenu\u003e-+- ADD -+- fieldname -|
       +- CORE ------*
       +- SEParator -------------------------------.
       '- dtext -+- rtext -------------------------|
                 +- MENU -- gname -----------------|
                 +- FORM -- fname -----------------|
                 +- CALLback -+- rtext ------------|
                 |            '--------------------|
                 '- TOGgle -+- rtext -.            |
                            '---------+- SELected -|
                                      '------------'--\u003e
```

## 노트 (Notes)
- 각 메뉴는 Main 메뉴 시스템의 일부이거나 Popup 메뉴 시스템의 일부여야 하며, 두 시스템에 동시에 속할 수는 없습니다.
- 설정(setup) 시 POPUP이나 MAIN을 지정하지 않으면, 메뉴의 용도는 처음에 알 수 없는 상태가 됩니다. 시스템은 해당 메뉴를 참조하는 첫 번째 동작에서 용도 유형을 추론하려고 시도합니다.
- Main 시스템의 메뉴는 한 번만 나타날 수 있습니다. 즉, 메인 시스템 메뉴는 여러 메뉴의 하위 메뉴(sub-menu)가 될 수 없습니다.
- Popup 시스템의 메뉴는 특정 팝업 트리에서 한 번만 나타날 수 있지만, 여러 팝업 트리에서 사용될 수는 있습니다.
- 메뉴는 자기 자신을 참조할 수 없습니다. 이는 자신의 필드 중 하나에서 직접적으로 pullright로 참조하거나, 자신의 메뉴 트리에 있는 다른 메뉴의 pullright가 되는 경우 모두를 포함합니다.
- 선택적 필드 이름(field-name)을 사용하여 메뉴 필드를 추가할 수 있습니다. 필드 이름을 지정하지 않으면 나중에 해당 필드를 참조할 수 없습니다.
- 필드가 코어 코드(core-code)에 의해 관리됨을 나타내기 위해 특별한 필드 유형(CORESEPARATOR, CORECALLBACK, COREFORM, COREMENU, CORETOGGLE)을 사용할 수 있습니다. 코어 관리 필드에 대해서는 콜백 함수를 지정할 필요가 없습니다.