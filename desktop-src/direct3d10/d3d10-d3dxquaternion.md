---
Description: Describes a quaternion.
ms.assetid: e6cb45b2-3132-4315-b02d-a3dfc444f8cc
title: D3DXQUATERNION structure
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# D3DXQUATERNION structure

Describes a quaternion.

## Syntax


```C++
typedef struct D3DXQUATERNION {
  FLOAT x;
  FLOAT y;
  FLOAT z;
  FLOAT w;
} D3DXQUATERNION, *LPD3DXQUATERNION;
```



## Members

<dl> <dt>

**x**
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

</dd> <dd>

The x-component.

</dd> <dt>

**y**
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

</dd> <dd>

The y-component.

</dd> <dt>

**z**
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

</dd> <dd>

The z-component.

</dd> <dt>

**w**
</dt> <dd>

Type: **[**FLOAT**](winprog.windows_data_types)**

</dd> <dd>

The w-component.

</dd> </dl>

## Remarks

Quaternions add a fourth element to the \[ x, y, z\] values that define a vector, resulting in arbitrary 4D vectors. However, the following illustrates how each element of a unit quaternion relates to an axis-angle rotation (where q represents a unit quaternion (x, y, z, w), axis is normalized, and theta is the desired CCW rotation about the axis):


```
q.x = sin(theta/2) * axis.x
q.y = sin(theta/2) * axis.y
q.z = sin(theta/2) * axis.z
q.w = cos(theta/2)
```



## Requirements



|                   |                                                                                         |
|-------------------|-----------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>D3DX10Math.h</dt> </dl> |



## See also

<dl> <dt>

[D3DX Structures](d3d10-graphics-reference-d3dx10-structures.md)
</dt> </dl>

 

 



