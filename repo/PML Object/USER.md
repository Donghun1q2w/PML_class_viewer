---
tags: [PML2, E3D, PMLUSERLOGIN, Security, Login, Script]
aliases: [PMLUSERLOGIN Object]
classification: PDMS Objects
---

# [[PMLUSERLOGIN]]

## 개요
PMLUSERLOGIN 오브젝트는 현재 로그인한 사용자에 대해서만 프로젝트 진입 스크립트를 생성할 수 있게 해주며, 이는 사용자 이름과 비밀번호를 입력할 필요가 없음을 의미한다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **PMLUserLogin**( ) | PMLUSERLOGIN | 이 오브젝트의 인스턴스를 생성한다. (Constructor) |
| **Macro**(STRING) | NO RESULT | 매크로의 전체 경로를 지정하는 STRING을 사용하여 실행할 매크로를 설정한다. |
| **MDB**(STRING) | NO RESULT | 로그인 MDB를 설정한다. |
| **Project**(STRING) | NO RESULT | 로그인 프로젝트를 설정한다. |
| **SaveToFile**(STRING) | NO RESULT | 암호화하여 지정된 경로에 저장한다. |
| **VerifyNonInteractive**(BOOLEAN) | NO RESULT | TRUE가 전달되면, 생성된 매크로 실행 후 사용자 상호 작용이 발생하지 않는지 검증한다. |