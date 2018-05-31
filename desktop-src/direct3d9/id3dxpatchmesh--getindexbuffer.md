---
Description: Gets the mesh index buffer.
ms.assetid: d9152f3b-c8e6-4def-8cf1-a517ca4d34e7
title: ID3DXPatchMeshGetIndexBuffer method
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ID3DXPatchMesh::GetIndexBuffer method

Gets the mesh index buffer.

## Syntax


```C++
HRESULT GetIndexBuffer(
  [out, retval] LPDIRECT3DINDEXBUFFER9 *ppIB
);
```



## Parameters

<dl> <dt>

*ppIB* \[out, retval\]
</dt> <dd>

Type: **[**LPDIRECT3DINDEXBUFFER9**](/windows/win32/d3d9helper/nn-d3d9-idirect3dindexbuffer9?branch=master)\***

Pointer to the index buffer.

</dd> </dl>

## Return value

Type: **[**HRESULT**](455d07e9-52c3-4efb-a9dc-2955cbfd38cc)**

If the method succeeds, the return value is D3D\_OK. If the method fails, the return value can be one of the following: D3DERR\_INVALIDCALL, E\_OUTOFMEMORY.

## Remarks

The index buffer contains the vertex ordering in the vertex buffer. The index buffer is used to access the vertex buffer when the mesh is rendered.

## Requirements



|                    |                                                                                        |
|--------------------|----------------------------------------------------------------------------------------|
| Header<br/>  | <dl> <dt>D3DX9Mesh.h</dt> </dl> |
| Library<br/> | <dl> <dt>D3dx9.lib</dt> </dl>   |



## See also

<dl> <dt>

[ID3DXPatchMesh](id3dxpatchmesh.md)
</dt> </dl>

 

 



