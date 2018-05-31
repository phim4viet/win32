---
Description: Sets the contents of the buffer to the constant table.
ms.assetid: 6058795c-fa32-42aa-9a36-af0b7f6eed1d
title: ID3DXConstantTableSetValue method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXConstantTable::SetValue method

Sets the contents of the buffer to the constant table.

## Syntax


```C++
HRESULT SetValue(
  [in] LPDIRECT3DDEVICE9 pDevice,
  [in] D3DXHANDLE        hConstant,
  [in] LPCVOID           pData,
  [in] UINT              Bytes
);
```



## Parameters

<dl> <dt>

*pDevice* \[in\]
</dt> <dd>

Type: **[**LPDIRECT3DDEVICE9**](/windows/win32/d3d9helper/nn-d3d9-idirect3ddevice9?branch=master)**

Pointer to an [**IDirect3DDevice9**](/windows/win32/d3d9helper/nn-d3d9-idirect3ddevice9?branch=master) interface, representing the device associated with the constant table.

</dd> <dt>

*hConstant* \[in\]
</dt> <dd>

Type: **[D3DXHANDLE](dx9-graphics-reference-effects-constants.md)**

Unique identifier to a constant. See [D3DXHANDLE](dx9-graphics-reference-effects-constants.md).

</dd> <dt>

*pData* \[in\]
</dt> <dd>

Type: **[**LPCVOID**](winprog.windows_data_types)**

Buffer containing data.

</dd> <dt>

*Bytes* \[in\]
</dt> <dd>

Type: **[**UINT**](winprog.windows_data_types)**

Size of the buffer, in bytes.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is D3D\_OK. If the method fails, the return value can be D3DERR\_INVALIDCALL.

## Requirements



|                    |                                                                                          |
|--------------------|------------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Shader.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>     |



## See also

<dl> <dt>

[ID3DXConstantTable](id3dxconstanttable.md)
</dt> </dl>

 

 



