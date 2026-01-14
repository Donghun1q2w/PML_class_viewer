---
tags: [PML2, E3D, Reporting, .NET]
aliases: [PMLReport Object]
classification: Collection and Report Objects
---

# [[PMLReport]]

## 개요
이 Object는 디자이너가 생성한 새 보고서를 일괄 처리(batch)로 실행하는 데 사용된다. 인터페이스는 .NET ReportingAddin 어셈블리에서 사용할 수 있다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **PMLReport**() | PMLReport | 생성자. |
| **AddParameters** (ARRAY argNames, ARRAY argValues) | No Result | 인자 이름과 값으로 구성된 2개의 배열을 사용하여 보고서에 매개변수를 추가하며, 이는 매개변수화된 보고서를 생성하는 데 사용된다. |
| **AddScope** (STRING ancestorElements, STRING elements) | No Result | 쉼표로 구분된 조상(ancestor) 요소 목록과 요소 목록을 사용하여 데이터를 필터링할 스코프 값을 지정한다. |
| **AddScope** (STRING ancestorElements, STRING elements, BOOLEAN fully, REAL minX, REAL minY, REAL minZ, REAL maxX, REAL maxY, REAL maxZ) | No result | 쉼표로 구분된 조상 요소 목록과 요소 목록을 사용하여 데이터를 필터링할 스코프 값을 지정하며, 제한 상자(limit box)가 지정된 경우 전체 포함 여부(fully)와 함께 minX, minY, minZ, maxX, maxY, maxZ를 사용하여 제한 상자를 구성한다. |
| **ExportAsCsv** (STRING reportFileName, STRING destinationFilename) | No Result | 보고서를 csv 파일로 내보낸다. |
| **ExportAsPdf** (STRING reportFileName, STRING destinationFilename) | No Result | 보고서를 pdf 파일로 내보낸다. |
| **ExportAsXlsx** (STRING reportFileName, STRING destinationFilename) | No Result | 보고서를 Xlsx 파일로 내보낸다. |
| **ExportAsXls** (STRING reportFileName, STRING destinationFilename) | No Result | 보고서를 Xls 파일로 내보낸다. |
| **InitializePrinterSetting** () | No Result | 프린터 설정을 초기화한다. |
| **OpenReportManager**() | No result | 보고서 관리자를 연다. |
| **Print** (STRING reportFileName) | No result | 보고서 정의 파일의 이름을 전달하여 시스템에 정의된 프린터 설정으로 보고서를 인쇄한다. |
| **PrintDirect** (STRING reportFileName) | No Result | 사용자 정의 프린터 설정으로 보고서를 인쇄한다. |
| **PublishToAVEVANET** (STRING reportFileName, STRING pdfFilename) | No Result | 보고서를 PDF 파일 형식으로 AVEVA NET에 게시한다. |
| **RemoveParameters** () | No Result | 보고서에 적용된 매개변수를 제거한다. |
| **RemoveScope** () | No Result | 보고서에 적용된 스코프를 제거한다. |