---
tags: [PML2, E3D, Encryption, Security, Macro]
aliases: [PMLSECURELOGIN Object]
classification: PDMS Objects
---

# [[PMLSECURELOGIN]]

## 개요
PMLSECURELOGIN 객체는 암호화된 커맨드 스크립트 생성 기능을 제어하는 데 사용된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **PMLSecureLogin** ( ) | PMLSECURELOGIN | 이 객체의 인스턴스를 생성한다. |
| **EmbedMacro** (BOOLEAN) | NO RESULT | 지정된 매크로를 임베드(embed)한다. |
| **HasLicenceToEmbedMacro** ( ) | [[BOOLEAN\|BOOLEAN Object]] | EmbedMacro 기능을 사용할 수 있는 경우 TRUE를 반환한다. |
| **Macro** (STRING) | NO RESULT | 실행할 매크로를 설정한다. 여기서 STRING은 매크로의 전체 경로를 지정한다. |
| **MDB** (STRING) | NO RESULT | 로그인 MDB를 설정한다. |
| **Password** (STRING) | NO RESULT | 로그인 비밀번호를 설정한다. |
| **Project** (STRING) | NO RESULT | 로그인 프로젝트를 설정한다. |
| **SaveToFile** (STRING) | NO RESULT | 암호화하여 지정된 경로에 저장한다. |
| **User** (STRING) | NO RESULT | 로그인 사용자를 설정한다. |
| **VerifyAfter** (DATETIME) | NO RESULT | 지정된 날짜 이후인지 검증한다. |
| **VerifyBefore** (DATETIME) | NO RESULT | 지정된 날짜 이전인지 검증한다. |
| **VerifyHostnames** (ARRAY) | NO RESULT | 문자열 배열로 지정된 다수의 호스트 이름을 검증한다. |
| **VerifyWinusers** (ARRAY) | NO RESULT | 문자열 배열로 지정된 다수의 윈도우 사용자를 검증한다. |