---
title: Principal.UserId property
description: For scripting, gets or sets the user identifier that is required to run the tasks that are associated with the principal.
ms.assetid: b85a1f05-acb0-4b3c-bea0-393ad7c6a43d
keywords:
- UserId property Task Scheduler
- UserId property Task Scheduler , Principal object
- Principal object Task Scheduler , UserId property
topic_type:
- apiref
api_name:
- Principal.UserId
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

# Principal.UserId property

For scripting, gets or sets the user identifier that is required to run the tasks that are associated with the principal.

## Syntax


```VB
Principal.UserId As String
```



## Property value

The user identifier that is required to run the task.

## Remarks

Do not set this property if a group identifier is specified in the [**GroupId**](principal-groupid.md) property.

When reading or writing XML for a task, the user identifier for the principal is specified using the [**UserId**](taskschedulerschema-userid-principaltype-element.md) element of the Task Scheduler schema.

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
</dt> <dt>

[**Principal**](principal.md)
</dt> <dt>

[**Principal.GroupId**](principal-groupid.md)
</dt> </dl>

 

 




