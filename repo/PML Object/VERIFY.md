---
tags: [PML2, E3D, Security, Verification, Login]
aliases: [VERIFY Object]
classification: PDMS Object
---

# [[VERIFY]]

## 개요
VERIFY Object는 실행 중인 사용자가 승인된 사용자 목록에 있는지, 승인된 호스트 컴퓨터에서 실행 중인지, 그리고 주어진 기간 내에 실행 중인지를 직접 확인하는 데 사용된다. 조건이 충족되지 않으면 명령 스크립트는 "Verification error"와 함께 즉시 종료된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **Verify** ( ) | PMLUSERLOGIN | 이 객체의 인스턴스를 생성한다. |
| **After** (DATETIME) | NO RESULT | 지정된 날짜 이후인지 확인한다. |
| **Before** (DATETIME) | NO RESULT | 지정된 날짜 이전인지 확인한다. |
| **Hostname** (STRING) | NO RESULT | 현재 컴퓨터 호스트 이름이 STRING으로 전달된 단일 호스트 이름과 일치하는지 확인한다. |
| **Hostname** (ARRAY) | NO RESULT | 현재 컴퓨터 호스트 이름이 STRING 배열로 전달된 호스트 이름 세트 중 하나와 일치하는지 확인한다. |
| **WinUser** (STRING) | NO RESULT | 현재 Windows 사용자가 STRING으로 전달된 단일 사용자 이름과 일치하는지 확인한다. |
| **WinUser** (ARRAY) | NO RESULT | 현재 Windows 사용자가 STRING 배열로 전달된 사용자 이름 세트 중 하나와 일치하는지 확인한다. |