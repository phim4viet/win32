---
title: ICatAdm CatalogName property
description: Contains the case-insensitive name of the catalog.
ms.assetid: a2dfb528-79b9-4ebf-9cdf-6621a57df30a
keywords:
- CatalogName property Indexing Service
- CatalogName property Indexing Service , ICatAdm interface
- ICatAdm interface Indexing Service , CatalogName property
topic_type:
- apiref
api_name:
- ICatAdm.CatalogName
- ICatAdm.get_CatalogName
api_location:
- Ciodm.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ICatAdm::CatalogName property

\[Indexing Service is no longer supported as of Windows XP and is unavailable for use as of Windows 8. Instead, use [Windows Search](https://msdn.microsoft.com/library/windows/desktop/aa965362) for client side search and [Microsoft Search Server Express]( http://go.microsoft.com/fwlink/p/?linkid=258445) for server side search.\]

Contains the case-insensitive name of the catalog.

This property is read-only.

## Syntax


```C++
HRESULT get_CatalogName(
  [out, retval] BSTR *pVal
);
```



## Property value

The case-insensitive name of the catalog.

## Requirements



|                                     |                                                                                      |
|-------------------------------------|--------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 2000 Professional \[desktop apps only\]<br/>                           |
| Minimum supported server<br/> | Windows 2000 Server \[desktop apps only\]<br/>                                 |
| End of client support<br/>    | Windows 7<br/>                                                                 |
| End of server support<br/>    | Windows Server 2008 R2<br/>                                                    |
| DLL<br/>                      | <dl> <dt>Ciodm.dll</dt> </dl> |



## See also

<dl> <dt>

[**ICatAdm**](icatadm.md)
</dt> </dl>

 

 




