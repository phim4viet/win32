---
title: AtaPortRegistryChannelSubKeyWriteDeferred routine
description: The AtaPortRegistryChannelSubKeyWriteDeferred routine writes data asynchronously to the indicated value name under the registry key HKLM\\CurrentControlSet\\Services\\ service name \\ControllerN\\ChannelM, where N is the number of the controller and M is the number of the channel.Note The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
ms.assetid: 332f6921-1ad2-42ae-9728-001f243b8cff
keywords:
- AtaPortRegistryChannelSubkeyWriteDeferred routine Storage Devices
topic_type:
- apiref
api_name:
- AtaPortRegistryChannelSubkeyWriteDeferred
api_location:
- irb.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# AtaPortRegistryChannelSubKeyWriteDeferred routine

The **AtaPortRegistryChannelSubKeyWriteDeferred** routine writes data asynchronously to the indicated value name under the registry key **HKLM\\CurrentControlSet\\Services\\***&lt;service name&gt;***\\Controller***N*\\**Channel***M*, where *N* is the number of the controller and *M* is the number of the channel.

> [!Note]  
> The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the [Storport driver](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver) and [Storport miniport](https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers) driver models.

 

## Syntax


```C++
BOOLEAN __inline AtaPortRegistryChannelSubkeyWriteDeferred(
  _In_ PVOID  ChannelExtension,
  _In_ UCHAR  ControllerNumber,
  _In_ PCHAR  ValueName,
  _In_ UCHAR  ValueType,
  _In_ PUCHAR Buffer,
  _In_ PULONG Length
);
```



## Parameters

<dl> <dt>

*ChannelExtension* \[in\]
</dt> <dd>

A pointer to the channel extension.

</dd> <dt>

*ControllerNumber* \[in\]
</dt> <dd>

Contains the controller number.

</dd> <dt>

*ValueName* \[in\]
</dt> <dd>

Contains the name of the registry value to write to.

</dd> <dt>

*ValueType* \[in\]
</dt> <dd>

Indicates the type of data that is contained in the registry value. This member should be assigned one of values indicated in the following table.



| Value                       | Meaning                                        |
|-----------------------------|------------------------------------------------|
| IDE\_REG\_DWORD<br/>  | A 4-byte numeric value. <br/>            |
| IDE\_REG\_BINARY<br/> | Binary data. <br/>                       |
| IDE\_REG\_SZ<br/>     | A null-terminated. Unicode string. <br/> |



 

</dd> <dt>

*Buffer* \[in\]
</dt> <dd>

Pointer to the source buffer that contains the data to be written to the registry.

</dd> <dt>

*Length* \[in\]
</dt> <dd>

A pointer to the number of bytes of data to copy. If the operation fails, the location that is pointed to by *Length* will update to the length of the data that was successfully written to the registry.

</dd> </dl>

## Return value

**AtaPortRegistryChannelSubKeyWriteDeferred** returns **TRUE** if the operation. Otherwise, it returns **FALSE**. The routine also returns **FALSE** if the miniport driver does not call it from the correct routine.

## Remarks

If the value name is not present, **AtaPortRegistryChannelSubKeyWriteDeferred** creates an entry for the value and the data is stored in the newly created value.

The buffer that is pointed to by *Buffer* must be allocated by using [**AtaPortRegistryAllocateBuffer**](ataportregistryallocatebuffer.md).

The miniport driver can call **AtaPortRegistryChannelSubKeyWriteDeferred** from any of the key routines that belong to its channel interface.

The miniport driver must not reuse the buffer that is pointed to by *Buffer* after the initial call to **AtaPortRegistryChannelSubKeyWriteDeferred**. Because the call is asynchronous, *Buffer* might still point to data that has not been flushed to the registry. The port driver flushes the data in the buffer to the registry when the miniport driver calls [**AtaPortRegistryFreeBuffer**](ataportregistryfreebuffer.md).

## Requirements



|                            |                                                                                                           |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Target platform<br/> | <dl> <dt>Desktop</dt> </dl>                        |
| Header<br/>          | <dl> <dt>Irb.h (include Ata.h or Irb.h)</dt> </dl> |



## See also

<dl> <dt>

[**AtaPortRegistryAllocateBuffer**](ataportregistryallocatebuffer.md)
</dt> <dt>

[**AtaPortRegistryFreeBuffer**](ataportregistryfreebuffer.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20AtaPortRegistryChannelSubKeyWriteDeferred%20routine%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





