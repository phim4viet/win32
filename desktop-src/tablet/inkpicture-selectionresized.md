---
Description: Occurs when the size of the current selection has changed, for example through alterations to the user interface, cut-and-paste procedures, or the Selection property.
ms.assetid: 4e7f461f-2909-40ab-98d8-b763d489eb62
title: InkPicture.SelectionResized event
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# InkPicture.SelectionResized event

Occurs when the size of the current selection has changed, for example through alterations to the user interface, cut-and-paste procedures, or the [**Selection**](/windows/win32/msinkaut/?branch=master) property.

## Syntax


```C++
void SelectionResized(
  [in] IInkRectangle *OldSelectionRect
);
```



## Parameters

<dl> <dt>

*OldSelectionRect* \[in\]
</dt> <dd>

The bounding rectangle of the selected [InkStrokes](/windows/win32/msinkaut/?branch=master) collection as it existed before the **SelectionResized** event fired.

> [!Note]  
> This rectangle is specified in ink space coordinates, which allows for undo scenarios.

 

</dd> </dl>

## Return value

This event does not return a value.

## Remarks

This event method is defined in the **\_IInkOverlayEvents** and **\_IInkPictureEvents** dispatch-only interfaces (dispinterfaces) with an ID of DISPID\_IOESelectionResized.

## Requirements



|                                     |                                                                                                                     |
|-------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows XP Tablet PC Edition \[desktop apps only\]<br/>                                                       |
| Minimum supported server<br/> | None supported<br/>                                                                                           |
| Header<br/>                   | <dl> <dt>Msinkaut.h (also requires Msinkaut\_i.c)</dt> </dl> |
| Library<br/>                  | <dl> <dt>InkObj.dll</dt> </dl>                               |



## See also

<dl> <dt>

[InkPicture](inkpicture-control-reference.md)
</dt> <dt>

[**Selection Property \[InkPicture Control\]**](/windows/win32/msinkaut/?branch=master)
</dt> <dt>

[**InkRectangle Class**](/windows/win32/msinkaut/?branch=master)
</dt> </dl>

 

 



