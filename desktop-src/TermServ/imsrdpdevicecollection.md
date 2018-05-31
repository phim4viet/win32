---
title: IMsRdpDeviceCollection interface
description: Represents a collection of device objects.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 9731b16b-12e0-457e-a4e5-a55d8a6db582
ms.prod: windows-server-dev
ms.technology: remote-desktop-services
ms.tgt_platform: multiple
keywords:
- IMsRdpDeviceCollection interface Remote Desktop Services
- IMsRdpDeviceCollection interface Remote Desktop Services , described
topic_type:
- apiref
api_name:
- IMsRdpDeviceCollection
api_location:
- MsTscAx.dll
api_type:
- COM
ms.date: 05/31/2018
ms.topic: interface
ms.author: windowssdkdev
---

# IMsRdpDeviceCollection interface

Represents a collection of device objects.

## Members

The **IMsRdpDeviceCollection** interface inherits from the [**IUnknown**](https://msdn.microsoft.com/library/windows/desktop/ms680509) interface. **IMsRdpDeviceCollection** also has these types of members:

-   [Methods](#methods)
-   [Properties](#properties)

### Methods

The **IMsRdpDeviceCollection** interface has these methods.



| Method                                                        | Description                                                 |
|:--------------------------------------------------------------|:------------------------------------------------------------|
| [**RescanDevices**](imsrdpdevicecollection-rescandevices.md) | Refreshes the list of objects in the collection.<br/> |



 

### Properties

The **IMsRdpDeviceCollection** interface has these properties.



| Property                                                                 | Access type          | Description                                                    |
|:-------------------------------------------------------------------------|:---------------------|:---------------------------------------------------------------|
| [**DeviceById**](imsrdpdevicecollection-devicebyid.md)<br/>       | Read-only<br/> | Retrieves the device with the specified identifier.<br/> |
| [**DeviceByIndex**](imsrdpdevicecollection-devicebyindex.md)<br/> | Read-only<br/> | Retrieves the device at the specified index.<br/>        |
| [**DeviceCount**](imsrdpdevicecollection-devicecount.md)<br/>     | Read-only<br/> | Retrieves the count of objects in the collection.<br/>   |



 

## Requirements



|                                     |                                                                                           |
|-------------------------------------|-------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                  |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                            |
| Type library<br/>             | <dl> <dt>MsTscAx.dll</dt> </dl>    |
| DLL<br/>                      | <dl> <dt>MsTscAx.dll</dt> </dl>    |
| IID<br/>                      | IID\_IMsRdpDeviceCollection is defined as 56540617-d281-488c-8738-6a8fdf64a118<br/> |



## See also

<dl> <dt>

[Remote Desktop Web Connection Reference](remote-desktop-web-connection-reference.md)
</dt> <dt>

[**IMsRdpDevice**](imsrdpdevice.md)
</dt> </dl>

 

 




