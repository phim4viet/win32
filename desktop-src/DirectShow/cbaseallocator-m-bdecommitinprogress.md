---
Description: Flag indicating whether a decommit operation is in progress.
ms.assetid: aa008be1-8faa-4dc1-9641-37dcc59ce6c7
title: CBaseAllocatorm\_bDecommitInProgress member
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CBaseAllocator::m\_bDecommitInProgress member

Flag indicating whether a decommit operation is in progress. The value is **TRUE** after the [**CBaseAllocator::Decommit**](cbaseallocator-decommit.md) method is called, but before all the buffers have been released. If the value is **TRUE**, the [**CBaseAllocator::GetBuffer**](cbaseallocator-getbuffer.md) method fails. Also, the allocator should not deleted itself while the value is **TRUE**.

## Syntax


```C++
BOOL m_bDecommitInProgress;
```



## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Amfilter.h (include Streams.h)</dt> </dl>                                                                                  |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CBaseAllocator Class**](cbaseallocator.md)
</dt> </dl>

 

 



