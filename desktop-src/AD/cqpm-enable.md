---
title: CQPM\_ENABLE message
description: Sent to the CQPageProc callback function of a query form extension page to enable or disable the page.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: dc75fab7-6de7-4138-86df-84d44e774120
ms.prod: windows-server-dev
ms.technology: active-directory-domain-services
ms.tgt_platform: multiple
keywords:
- CQPM_ENABLE message Active Directory
topic_type:
- apiref
api_name:
- CQPM_ENABLE
api_location:
- Cmnquery.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# CQPM\_ENABLE message

The **CQPM\_ENABLE** message is sent to the [**CQPageProc**](/windows/win32/Cmnquery/nc-cmnquery-lpcqpageproc?branch=master) callback function of a query form extension page to enable or disable the page.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Contains zero to disable the page or nonzero to enable the page.

</dd> <dt>

*lParam* 
</dt> <dd>

Not used.

</dd> </dl>

## Return value

The return value for this message is ignored.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                              |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                        |
| Header<br/>                   | <dl> <dt>Cmnquery.h</dt> </dl> |



## See also

<dl> <dt>

[**CQPageProc**](/windows/win32/Cmnquery/nc-cmnquery-lpcqpageproc?branch=master)
</dt> </dl>

 

 




