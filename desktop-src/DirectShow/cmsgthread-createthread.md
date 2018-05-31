---
Description: Creates a thread.
ms.assetid: 40785522-dc6e-41af-8b27-9e8875a0dd84
title: CMsgThread.CreateThread method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CMsgThread.CreateThread method

Creates a thread.

## Syntax


```C++
BOOL CreateThread();
```



## Parameters

This method has no parameters.

## Return value

Returns one of the following values.



| Return code                                                                              | Description                                     |
|------------------------------------------------------------------------------------------|-------------------------------------------------|
| <dl> <dt>****TRUE****</dt> </dl>  | Thread was successfully created.<br/>     |
| <dl> <dt>****FALSE****</dt> </dl> | Thread was not successfully created.<br/> |



 

## Remarks

The thread will loop, blocking until a request is queued (through the [**CMsgThread::PutThreadMsg**](cmsgthread-putthreadmsg.md) member function) and then calling the [**CMsgThread::ThreadMessageProc**](cmsgthread-threadmessageproc.md) member function with each message.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Msgthrd.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CMsgThread Class**](cmsgthread.md)
</dt> </dl>

 

 



