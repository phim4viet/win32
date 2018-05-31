---
title: TaskSettings.WakeToRun property
description: For scripting, gets or sets a Boolean value that indicates that the Task Scheduler will wake the computer when it is time to run the task.
ms.assetid: efa1c7cd-7a70-4760-909f-bb5a1ede35f4
keywords:
- WakeToRun property Task Scheduler
- WakeToRun property Task Scheduler , TaskSettings object
- TaskSettings object Task Scheduler , WakeToRun property
topic_type:
- apiref
api_name:
- TaskSettings.WakeToRun
api_location:
- taskschd.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# TaskSettings.WakeToRun property

For scripting, gets or sets a Boolean value that indicates that the Task Scheduler will wake the computer when it is time to run the task.

This property is read/write.

## Syntax


```VB
TaskSettings.WakeToRun As Boolean
```



## Property value

If True, the property indicates that the Task Scheduler will wake the computer when it is time to run the task.

## Remarks

When the Task Scheduler service wakes the computer to run a task, the screen may remain off even though the computer is no longer in the sleep or hibernate mode. The screen will turn on when Windows Vista detects that a user has returned to use the computer.

When reading or writing XML for a task, this setting is specified in the [**WakeToRun**](taskschedulerschema-waketorun-settingstype-element.md) element of the Task Scheduler schema.

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                          |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                    |
| Type library<br/>             | <dl> <dt>Taskschd.tlb</dt> </dl> |
| DLL<br/>                      | <dl> <dt>Taskschd.dll</dt> </dl> |



## See also

<dl> <dt>

[Task Scheduler](task-scheduler-start-page.md)
</dt> </dl>

 

 




