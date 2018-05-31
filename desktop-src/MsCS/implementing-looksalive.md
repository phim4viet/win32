---
title: Implementing LooksAlive
description: If you do not implement asynchronous failure detection for a resource type, the Resource Monitor calls the LooksAlive entry point function for each instance of that type.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 436d99c7-91ab-4ecd-9ee3-f42887c00407
ms.prod: windows-server-dev
ms.technology: failover-clustering
ms.tgt_platform: multiple
keywords:
- entry point functions Failover Cluster ,implementing LooksAlive
- LooksAlive Failover Cluster ,implementing
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Implementing LooksAlive

If you do not implement asynchronous failure detection for a [resource type](resource-types.md), the [Resource Monitor](resource-monitor.md) calls the [**LooksAlive**](/windows/previous-versions/ResApi/nc-resapi-plooks_alive_routine?branch=master) entry point function for each instance of that type. The [**LooksAlivePollInterval**](resources-looksalivepollinterval.md) property controls the frequency of these calls. If **LooksAlive** returns **FALSE**, [**IsAlive**](/windows/previous-versions/ResApi/nc-resapi-pis_alive_routine?branch=master) will be called immediately.

**To implement LooksAlive**

1.  Required: The [**LooksAlive**](/windows/previous-versions/ResApi/nc-resapi-plooks_alive_routine?branch=master) entry point function can be called concurrently with the [*Terminate*](/windows/previous-versions/ResApi/nc-resapi-pterminate_routine?branch=master) entry point function. Any resources that are accessed by both entry points must be properly guarded.

2.  Recommended: Perform one or more very fast, cursory checks of the specified instance with the emphasis on detecting potential problems rather than verifying operational status. [**IsAlive**](/windows/previous-versions/ResApi/nc-resapi-pis_alive_routine?branch=master) will determine whether the instance is really operational.
3.  Recommended: Adjust the [**LooksAlivePollInterval**](resources-looksalivepollinterval.md) property to an appropriate value.
4.  Recommended. Take no more than 300 milliseconds to return a value.

## Example

See [Resource DLL Examples](https://msdn.microsoft.com/library/aa370474).

 

 



