---
tags: [PML2, E3D, PDMS, UNDOABLE, History, Database]
aliases: [UNDOABLE Object]
classification: PDMS Objects
---

# [[UNDOABLE]]

## 개요
이 객체는 undo(실행 취소) 및 redo(다시 실행) 스택에 기능을 추가할 수 있게 해줍니다.

## 메소드 (Methods)

| Name                     | Result    | Purpose                                                       |
| :----------------------- | :-------- | :------------------------------------------------------------ |
| **description** (STRING) | NO RESULT | Undoable에 설명 텍스트를 추가한다.                                       |
| **add** ()               | NO RESULT | 데이터베이스에 설명 텍스트로 표시(mark)를 하고, 이 undoable을 undo 스택에 추가한다.      |
| **endundoable** ()       | NO RESULT | 변경의 끝부분에 데이터베이스에 다시 표시(mark)를 한다.                             |
| **undoAction** (STRING)  | NO RESULT | 이 undoable이 undo 스택에서 꺼내질 때 실행될 커맨드를 지정한다.                    |
| **redoAction** (STRING)  | NO RESULT | 이 undoable이 redo 스택에서 꺼내질 때 실행될 커맨드를 지정한다.                    |
| **clearAction** (STRING) | NO RESULT | 연관된 undo/redo 수행 없이 이 undoable이 지워질(cleared) 때 실행될 커맨드를 지정한다. |