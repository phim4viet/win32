---
Description: Indicates that the suspend process is starting and resources should be brought into a consistent state.
ms.assetid: 5cf3d249-3d8b-4596-9d8b-e7b95a270eff
title: IMFCdmSuspendNotifyBegin method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IMFCdmSuspendNotify::Begin method

Indicates that the suspend process is starting and resources should be brought into a consistent state.

## Syntax


```C++
HRESULT Begin();
```



## Parameters

This method has no parameters.

## Return value

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Requirements



|                                     |                                                                                              |
|-------------------------------------|----------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 8.1 \[desktop apps only\]<br/>                                                 |
| Minimum supported server<br/> | Windows Server 2012 R2 \[desktop apps only\]<br/>                                      |
| IDL<br/>                      | <dl> <dt>Mfmediaengine.idl</dt> </dl> |



## See also

<dl> <dt>

[**IMFCdmSuspendNotify**](/windows/win32/mfmediaengine/nn-mfmediaengine-imfcdmsuspendnotify?branch=master)
</dt> </dl>

 

 



