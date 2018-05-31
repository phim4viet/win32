---
title: IOCTL\_MOUNTDEV\_LINK\_CREATED control code
description: Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.
ms.assetid: 98ccf623-8232-4bcb-bd72-39dd31c7ede3
keywords:
- IOCTL_MOUNTDEV_LINK_CREATED control code Storage Devices
topic_type:
- apiref
api_name:
- IOCTL_MOUNTDEV_LINK_CREATED
api_location:
- mountdev.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IOCTL\_MOUNTDEV\_LINK\_CREATED control code

Support for this IOCTL by the mount manager clients is optional. The mount manager uses this IOCTL to alert the client driver that a persistent name has been assigned to its volume. The input for this IOCTL is the persistent name assigned.

## Input Buffer

The mount point manager places a variable-length structure of type [**MOUNTDEV\_NAME**](mountdev-name.md), defined in *Mountmgr.h*, at the beginning of the buffer at **Irp-&gt;AssociatedIrp.SystemBuffer**. The mount manager inserts the persistent name just assigned at the address pointed to by the *Name* member of this structure.

## Input Buffer Length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to **sizeof**(MOUNTDEV\_NAME).

## Output Buffer

None

## Output Buffer Length

None

## Status block

No status.

## Requirements



|                   |                                                                                                            |
|-------------------|------------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Mountdev.h (include Mountmgr.h)</dt> </dl> |



## See also

<dl> <dt>

[**MOUNTDEV\_NAME**](mountdev-name.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20IOCTL_MOUNTDEV_LINK_CREATED%20control%20code%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





