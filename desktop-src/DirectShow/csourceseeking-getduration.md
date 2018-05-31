---
Description: The GetDuration method retrieves the duration of the stream. This method implements the IMediaSeekingGetDuration method.
ms.assetid: 074eb2d0-a7a3-4bc1-82e8-2f42c6d43dac
title: CSourceSeeking.GetDuration method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# CSourceSeeking.GetDuration method

The `GetDuration` method retrieves the duration of the stream. This method implements the [**IMediaSeeking::GetDuration**](/windows/win32/Strmif/nf-strmif-imediaseeking-getduration?branch=master) method.

## Syntax


```C++
HRESULT GetDuration(
   LONGLONG *pDuration
);
```



## Parameters

<dl> <dt>

*pDuration* 
</dt> <dd>

Pointer to a variable that receives the duration, in units of the current time format.

</dd> </dl>

## Return value

Returns one of the **HRESULT** values listed in the following table.



| Return code                                                                               | Description                       |
|-------------------------------------------------------------------------------------------|-----------------------------------|
| <dl> <dt>**S\_OK**</dt> </dl>      | Success<br/>                |
| <dl> <dt>**E\_POINTER**</dt> </dl> | **NULL** pointer value<br/> |



 

## Remarks

The duration is specified by the [**CSourceSeeking::m\_rtDuration**](csourceseeking-m-rtduration.md) member variable.

## Requirements



|                    |                                                                                                                                                                                            |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>Ctlutil.h (include Streams.h)</dt> </dl>                                                                                   |
| Library<br/> | <dl> <dt>Strmbase.lib (retail builds); </dt> <dt>Strmbasd.lib (debug builds)</dt> </dl> |



## See also

<dl> <dt>

[**CSourceSeeking Class**](csourceseeking.md)
</dt> </dl>

 

 



