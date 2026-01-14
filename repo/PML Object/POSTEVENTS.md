---
tags: [PML2, E3D, Event, Undo, Redo, 3D Geometry Objects]
aliases: [POSTEVENTS Object]
classification: 3D Geometry Objects
---

# [[POSTEVENTS]]

## 개요
사용자는 아래에 설명된 메소드를 제공하는 PostEvents 오브젝트를 정의할 수 있으며, 이 기능을 사용하려면 이 유형의 전역(global) 오브젝트를 생성하고 이름을 `!!postEvents`로 지정해야 한다. 이 오브젝트의 메소드는 MARKDB 명령, undoable 오브젝트 또는 코어 기능에 의해 실행 취소 가능(undoable) 항목이 생성되어 실행 취소 스택에 추가되거나, Undo 또는 Redo가 발생할 때 호출된다. 각 메소드에는 해당 작업(mark, undo, redo)과 연관된 마크의 이름을 포함하는 STRING 오브젝트가 전달된다.

## 메소드 (Methods)

| Name | Result | Purpose |
| :--- | :--- | :--- |
| **postMark** (STRING) | NO RESULT | 실행 취소 가능(undoable) 항목이 실행 취소 스택(undo stack)에 추가된 후 호출된다. STRING은 undoable 오브젝트와 연관된 설명 텍스트이다. |
| **postUndo** (STRING) | NO RESULT | 실행 취소(undo)가 발생한 후 호출된다. STRING은 undoable 오브젝트와 연관된 설명 텍스트이다. |
| **postRedo** (STRING) | NO RESULT | 재실행(redo)이 발생한 후 호출된다. STRING은 undoable 오브젝트와 연관된 설명 텍스트이다. |
| **postClearMark** () | NO RESULT | clearMark가 발생한 후 호출된다. |
| **postClearAll** () | NO RESULT | clearAll이 발생한 후 호출된다. |