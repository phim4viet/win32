---
title: ID3DX11EffectType GetMemberTypeBySemantic method
description: Get a member type by semantic.
ms.assetid: d5fea2d9-8d08-4e02-a9c6-dbcfaaf4a7d1
keywords:
- GetMemberTypeBySemantic method Direct3D 11
- GetMemberTypeBySemantic method Direct3D 11 , ID3DX11EffectType interface
- ID3DX11EffectType interface Direct3D 11 , GetMemberTypeBySemantic method
topic_type:
- apiref
api_name:
- ID3DX11EffectType.GetMemberTypeBySemantic
api_location:
- N/A
- N/A.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DX11EffectType::GetMemberTypeBySemantic method

Get a member type by semantic.

## Syntax


```C++
ID3DX11EffectType* GetMemberTypeBySemantic(
   LPCSTR Semantic
);
```



## Parameters

<dl> <dt>

*Semantic* 
</dt> <dd>

Type: **[**LPCSTR**](https://msdn.microsoft.com/library/windows/desktop/aa383751)**

A semantic.

</dd> </dl>

## Return value

Type: **[**ID3DX11EffectType**](id3dx11effecttype.md)\***

A pointer to an [**ID3DX11EffectType**](id3dx11effecttype.md).

## Remarks

> [!Note]  
> The DirectX SDK does not supply any compiled binaries for effects. You must use Effects 11 source to build your effects-type application. For more information about using Effects 11 source, see [Differences Between Effects 10 and Effects 11](d3d11-graphics-programming-guide-effects-differences.md).

 

## Requirements



|                    |                                                                                                                                              |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3dx11effect.h</dt> </dl>                                                    |
| Library<br/> | <dl> <dt>N/A (An Effects 11 library is available online as shared source.)</dt> </dl> |



## See also

<dl> <dt>

[ID3DX11EffectType](id3dx11effecttype.md)
</dt> </dl>

 

 




