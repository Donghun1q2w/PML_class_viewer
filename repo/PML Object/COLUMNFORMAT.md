---
tags: [PML2, E3D, Collection, Report, Table]
aliases: [COLUMNFORMAT Object]
classification: Collection and Report Objects
---

# [[COLUMNFORMAT]]

## 개요
COLUMNFORMAT 오브젝트는 테이블 오브젝트의 컬럼이 채워지는 방식을 정의한다. 컬럼의 포맷팅은 컬럼 정의 자체와 분리되어, 테이블 오브젝트로부터 데이터를 추출하는 데 사용되는 리포트 오브젝트 내에 유지되어야 한다. 이를 통해 테이블을 재생성할 필요 없이 동일한 테이블에서 다양한 리포트를 생성할 수 있다.

## 메소드 (Methods)

| Name                    | Result  | Purpose                                                                                                                           |
| :---------------------- | :------ | :-------------------------------------------------------------------------------------------------------------------------------- |
| **ColumnFormat** ()     |         | 생성자 (모든 오브젝트 설정을 초기화함)                                                                                                            |
| **Format** (FORMAT)     |         | 컬럼의 포맷을 전달된 포맷으로 설정한다.                                                                                                            |
| **Format** (DATEFORMAT) |         | 컬럼의 포맷을 전달된 날짜 포맷으로 설정한다.                                                                                                         |
| **FORMAT** ('STRING')   |         | 컬럼의 포맷을 해제한다. 즉, 컬럼                                                                                                               |
| **Width** (REAL)        |         | 컬럼 너비를 설정한다.                                                                                                                      |
| **Widest** ()           |         | 최대 컬럼 너비 플래그를 설정하며, 특정 너비 값을 설정하면 자동으로 이 플래그가 FALSE로 설정된다. 가장 넓은 너비를 결정하기 위해 전체 스캔을 수행해야 하므로 Width에 대해 가장 효율적이지 않은 메소드임에 유의해야 한다. |
| **Indent** (REAL, REAL) |         | 컬럼의 왼쪽 및 오른쪽 들여쓰기(공백)를 설정한다.                                                                                                      |
| **Format** ()           | FORMAT  | 컬럼 내 숫자 값에 대한 포맷을 반환한다.                                                                                                           |
| **Width** ()            | REAL    | 컬럼 너비를 반환한다. 문자열이 컬럼 너비보다 크면 다음 줄로 래핑되고, 숫자 값이 컬럼 너비보다 크면 해시(#) 열로 출력된다.                                                          |
| **GetWidest** ()        | [[BOOLEAN\|BOOLEAN Object]] | “widest”가 설정되어 있으면 TRUE를 반환한다.                                                                                                    |
| **Justification** ()    | STRING  | 컬럼의 맞춤(justification)을 반환한다.                                                                                                      |
| **LeftIndent** ()       | REAL    | 왼쪽 들여쓰기 설정을 반환한다.                                                                                                                 |
| **RightIndent** ()      | REAL    | 오른쪽 들여쓰기 설정을 반환한다.                                                                                                                |