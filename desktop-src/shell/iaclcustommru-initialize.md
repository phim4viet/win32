---
Description: Loads a list of strings into the most recently used (MRU) list from the registry.
title: IACLCustomMRUInitialize method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IACLCustomMRU::Initialize method

Loads a list of strings into the most recently used (MRU) list from the registry.

## Syntax


```C++
HRESULT Initialize(
  [in] LPCWSTR pwszMRURegKey,
  [in] DWORD   dwMax
);
```



## Parameters

<dl> <dt>

*pwszMRURegKey* \[in\]
</dt> <dd>

Type: **LPCWSTR**

A pointer to a buffer containing the registry key holding the strings for the MRU list.

</dd> <dt>

*dwMax* \[in\]
</dt> <dd>

Type: **DWORD**

The maximum number of entries that can be taken from *pwszMRURegKey*.

</dd> </dl>

## Return value

Type: **HRESULT**

If this method succeeds, it returns **S\_OK**. Otherwise, it returns an **HRESULT** error code.

## Requirements



|                                     |                                                      |
|-------------------------------------|------------------------------------------------------|
| Minimum supported client<br/> | Windows XP \[desktop apps only\]<br/>          |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/> |



 

 



