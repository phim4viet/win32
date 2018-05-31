---
Description: The Pause method signals the streaming thread to become active.
ms.assetid: c97da113-c5a7-422d-9215-70b556e0b8ca
title: CSourceStream.Pause method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CSourceStream.Pause method

The `Pause` method signals the streaming thread to become active.

## Syntax


```C++
HRESULT Pause();
```



## Parameters

This method has no parameters.

## Return value

Returns S\_OK or E\_UNEXPECTED.

## Remarks

The [**CSourceStream::Active**](csourcestream-active.md) method calls this method. When the [**CSourceStream::ThreadProc**](csourcestream-threadproc.md) method receives this request, it calls the [**CSourceStream::DoBufferProcessingLoop**](csourcestream-dobufferprocessingloop.md) method.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Source.h (include Streams.h)</dt> </dl>                                                                                    |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CSourceStream Class**](csourcestream.md)
</dt> </dl>

 

 



