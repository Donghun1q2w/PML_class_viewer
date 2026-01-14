---
tags: [PML2, E3D, PDMS, SESSION]
aliases: [SESSION Object]
classification: PDMS Objects
---

# [[SESSION]]

## 개요
SESSION Object는 AVEVA PDMS/E3D 내의 세션 정보를 나타낸다. 현재 세션 또는 특정 세션의 고유 ID, 이름, 로그인 사용자, 호스트 머신 등의 정보를 조회하고 관리하는 데 사용된다.

## 멤버 (Members)

| Name | Type | Purpose |
| :--- | :--- | :--- |
| **UniqueID** | [[STRING\|STRING Object]] | 내부 ID (Internal ID) |
| **Name** | [[STRING\|STRING Object]] | 세션 이름 (Session Name) |
| **Login** | [[STRING\|STRING Object]] | 사용자의 로그인 ID (User’s login ID) |
| **Host** | [[STRING\|STRING Object]] | 세션을 실행 중인 머신의 ID (ID of the Machine running the session) |
| **Entered** | [[STRING\|STRING Object]] | 세션 진입 시간 (Time of entering the session) |
| **LocationName** | [[STRING\|STRING Object]] | 세션의 위치(Location) 이름 (Name of Location for Session) |
| **IsRemote** | [[STRING\|STRING Object]] | 원격 위치(Remote locations)의 세션인 경우 True (True for Sessions at Remote locations) |
| **IsCurrent** | [[BOOLEAN\|BOOLEAN Object]] | 사용자의 자체 SESSION object인 경우 TRUE (TRUE for User’s own SESSION object) |

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **SESSION** (STRING) | SESSION | 세션의 Unique-id를 포함하는 문자열이 주어졌을 때 SESSION object를 반환한다. |
| **ConfirmID** (STRING) | [[BOOLEAN\|BOOLEAN Object]] | STRING으로 지정된 암호가 현재 로그인한 사용자에게 올바른 경우 TRUE를 반환한다. (STRING 값은 선행 문자 ‘/’를 포함해야 한다). |
| **Current** () | ARRAY OF DB | SESSION object의 MDB에 있는 현재 DB 목록 (List of Current DBs in the MDB of the SESSION object). |
| **Deferred** () | ARRAY OF DB | SESSION object의 MDB에 있는 지연된(Deferred) DB 목록. |
| **Location** () | LOCATION | 세션이 적용되는 LOCATION을 반환한다. 비-Global(non-Global) 프로젝트에서는 NULL 또는 오류를 반환한다. |
| **MDB** () | MDB | SESSION의 현재 MDB. |
| **Mode** () | ARRAY OF STRING | 현재 DB 각각에 대한 잠재적 접근 모드 목록('R', 'RW' 또는 'N'). |
| **Modified** () | [[BOOLEAN\|BOOLEAN Object]] | 데이터베이스가 수정된 경우 TRUE. |
| **Module** () | [[STRING\|STRING Object]] | 현재 모듈의 이름. |
| **Status** () | ARRAY OF STRINGS | 현재 DB 각각에 대한 현재 접근 모드 목록('R', 'RW' 또는 'N'). |
| **User** () | USER | 이 SESSION object의 사용자(USER). |

## 커맨드 (Commands)

```pml
!SESSION = CURRENT SESSION  $ Returns the current session object.
```

## 노트 (Notes)
- LocationName 멤버와 Location() 메소드는 세션이 적용되는 위치를 의미한다. 이는 원격 위치에서의 세션이 요청된 경우를 제외하고는 일반적으로 현재 위치이다. 비-Global(non-Global) 프로젝트에서는 이러한 멤버와 메소드를 사용할 수 없거나 설정되지 않을 수 있다.
- Global 프로젝트의 일부 ADMIN 세션은 다른 위치의 시스템 데이터베이스에 적용될 수 있다. 이는 관련이 있는 경우 Module() 메소드에 의해 반환되는 문자열의 일부로 반환된다. 다른 ADMIN 세션은 실제로 Global Daemon 세션일 수 있으며, 이는 name 멤버의 문자열 일부로 반환된다.
- 일부 SESSION object 메소드는 제한적으로만 사용 가능하다:
    - Modified() 메소드는 현재 위치의 현재 세션에만 적용된다.
    - Current(), Deferred(), Mode() 및 Status() 메소드는 원격 세션에 대해 구현되지 않으며 오류를 반환한다.
    - Location(), MDB(), User() 및 Module() 메소드는 원격 세션에 대해 유효하다.
- 마지막 세 가지 메소드(Location, MDB, User, Module)는 원격 위치의 세션에 대해 데몬(Daemon) 활동을 유발한다.
- 원격 세션에 대해 MDB() 및 User() 메소드가 반환한 MDB 및 USER object를 사용할 때는 주의해야 한다. 이러한 object의 메소드는 현재 열려 있는 시스템 데이터베이스에 접근한다. 따라서 원격으로 생성된 MDB 및 USER object에서 메소드를 호출하기 전에 적절한 위치의 시스템 데이터베이스를 열어야 한다(ADMINISTER SYSTEM 명령 사용).