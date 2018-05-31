---
title: DDCCIGetCapabilitiesString function
description: Gets a string that describes the capabilities of a monitor.
ms.assetid: 54041126-b710-4448-a9f0-9b644d6b8186
keywords:
- DDCCIGetCapabilitiesString function Monitor Configuration
topic_type:
- apiref
api_name:
- DDCCIGetCapabilitiesString
api_location:
- gdi32.dll
api_type:
- DllExport
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# DDCCIGetCapabilitiesString function

> \[!Important\]  
> This function is used by the monitor configuration API to access functionality in the display driver. Applications should not call this function.

 

Gets a string that describes the capabilities of a monitor.

## Syntax


```C++
NTSTATUS WINAPI DDCCIGetCapabilitiesString(
  _In_  HANDLE hMonitor,
  _Out_ LPSTR  pszString,
  _In_  DWORD  dwLength
);
```



## Parameters

<dl> <dt>

*hMonitor* \[in\]
</dt> <dd>

A handle to a physical monitor.

</dd> <dt>

*pszString* \[out\]
</dt> <dd>

A pointer to a buffer that receives the capabilities string. To get the length of the capabilities string, call [**DDCCIGetCapabilitiesStringLength**](ddccigetcapabilitiesstringlength.md).

</dd> <dt>

*dwLength* \[in\]
</dt> <dd>

The size of the *pszString* buffer, in characters, including the terminating null character.

</dd> </dl>

## Return value

If the method succeeds, it returns **STATUS\_SUCCESS**. Otherwise, it returns an **NTSTATUS** error code.

## Remarks

Applications should call [**CapabilitiesRequestAndCapabilitiesReply**](/windows/win32/LowLevelMonitorConfigurationAPI/nf-lowlevelmonitorconfigurationapi-capabilitiesrequestandcapabilitiesreply?branch=master) instead of calling this function.

This function has no associated import library. To call this function, you must use the [**LoadLibrary**](https://msdn.microsoft.com/library/windows/desktop/ms684175) and [**GetProcAddress**](https://msdn.microsoft.com/library/windows/desktop/ms683212) functions to dynamically link to Gdi32.dll.

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                       |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                 |
| DLL<br/>                      | <dl> <dt>Gdi32.dll</dt> </dl> |



## See also

<dl> <dt>

[Monitor Configuration Functions](monitor-configuration-functions.md)
</dt> </dl>

 

 




