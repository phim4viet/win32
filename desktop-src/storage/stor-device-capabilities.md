---
title: STOR\_DEVICE\_CAPABILITIES structure
description: The STOR\_DEVICE\_CAPABILITIES structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB\_FUNCTION\_PNP.
ms.assetid: 62BE93C6-8E1C-4430-BB07-C25E8D4076B0
keywords:
- STOR_DEVICE_CAPABILITIES structure Storage Devices
- PSTOR_DEVICE_CAPABILITIES structure pointer Storage Devices
topic_type:
- apiref
api_name:
- STOR_DEVICE_CAPABILITIES
api_location:
- storport.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: structure
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# STOR\_DEVICE\_CAPABILITIES structure

The **STOR\_DEVICE\_CAPABILITIES** structure reports device capabilities to the Storport driver in response to a capabilities query in a SCSI request block (SRB) with a function of SRB\_FUNCTION\_PNP. **STOR\_DEVICE\_CAPABILITIES** is a subset of the [**DEVICE\_CAPABILITIES**](https://msdn.microsoft.com/library/windows/hardware/ff543095) structure containing the members relevant to storage devices.

## Syntax


```C++
typedef struct _STOR_DEVICE_CAPABILITIES {
  ULONG Version;
  ULONG DeviceD1  :1;
  ULONG DeviceD2  :1;
  ULONG LockSupported  :1;
  ULONG EjectSupported  :1;
  ULONG Removeable  :1;
  ULONG DockDevice  :1;
  ULONG UniqueID  :1;
  ULONG SilentInstall  :1;
  ULONG RawDeviceOK  :1;
  ULONG SurpriseRemovalOK  :1;
  ULONG NoDisplayInUI  :1;
} STOR_DEVICE_CAPABILITIES, *PSTOR_DEVICE_CAPABILITIES;
```



## Members

<dl> <dt>

**Version**
</dt> <dd>

Specifies the version of the structure. Set to STOR\_DEVICE\_CAPABILITIES\_EX\_VERSION\_1 by Storport.

</dd> <dt>

**DeviceD1**
</dt> <dd>

Specifies whether the device hardware supports the D1 power state. Miniport drivers set this bit to 0.

</dd> <dt>

**DeviceD2**
</dt> <dd>

Specifies whether the device hardware supports the D2 power state. Miniport drivers set this bit to 0.

</dd> <dt>

**LockSupported**
</dt> <dd>

Specifies whether the device supports physical-device locking that prevents device ejection. This member pertains to ejecting a LUN or a unit device.

</dd> <dt>

**EjectSupported**
</dt> <dd>

Specifies whether the device supports software-controlled device ejection while the system is in the **PowerSystemWorking** state. This member pertains to ejecting a LUN or unit device.

</dd> <dt>

**Removeable**
</dt> <dd>

Specifies whether the device can be dynamically removed from its immediate parent. If **Removable** is set to **TRUE**, the device does not belong to the same physical object as its parent.

If **Removable** is set to **TRUE**, the device is displayed in the Unplug or Eject Hardware program, unless **SurpriseRemovalOK** is also set to **TRUE**.

</dd> <dt>

**DockDevice**
</dt> <dd>

Specifies whether the device is a docking peripheral.

</dd> <dt>

**UniqueID**
</dt> <dd>

Specifies whether the device's instance ID is unique system-wide. This bit is clear if the instance ID is unique only within the scope of the bus.

</dd> <dt>

**SilentInstall**
</dt> <dd>

Specifies whether **Device Manager** should suppress all installation dialog boxes; except required dialog boxes such as "no compatible drivers found."

</dd> <dt>

**RawDeviceOK**
</dt> <dd>

Specifies whether the driver for the underlying bus can drive the device if there is no function driver (for example, SCSI devices in pass-through mode). This mode of operation is called raw mode.

</dd> <dt>

**SurpriseRemovalOK**
</dt> <dd>

Specifies whether the miniport driver for the device can handle the case where the device is removed before Storport can send SRB\_FUNCTION\_PNP with **StorRemoveDevice** as the **PnPAction** in the [**SCSI\_PNP\_REQUEST\_BLOCK**](scsi-pnp-request-block.md) structure. If **SurpriseRemovalOK** is set to **TRUE**, the device can be safely removed from its immediate parent regardless of the state that its driver is in.

</dd> <dt>

**NoDisplayInUI**
</dt> <dd>

Do not display the device in the user interface. If this bit is set, the device is never displayed in the user interface, even if the device is present but fails to start. Miniport drivers do not set this bit.

</dd> </dl>

## Remarks

When a miniport driver receives an SRB in its [**HwStorStartIo**](hwstorstartio.md) routine where the SRB function is SRB\_FUNCTION\_PNP, the SRB is formatted as a [**SCSI\_PNP\_REQUEST\_BLOCK**](scsi-pnp-request-block.md) structure. If the **PnPAction** member of the SRB is **StorQueryCapabilities**, the miniport can return a **STOR\_DEVICE\_CAPABILITIES** structure in the **DataBuffer** member of the SRB.

Storport sends this structure to the miniport with all members initialized to 0. On return, only the **Removable** field is used from this structure.

Starting with Windows 8, miniports should use the [**STOR\_DEVICE\_CAPABILITIES\_EX**](stor-device-capabilities-ex.md) structure to indicate support for additional capabilities.

## Requirements



|                    |                                                                                                                                  |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------|
| Version<br/> | Available starting with Windows Vista.<br/>                                                                                |
| Header<br/>  | <dl> <dt>Storport.h (include Storport.h, Minitape.h, or Srb.h)</dt> </dl> |



## See also

<dl> <dt>

[**DEVICE\_CAPABILITIES**](https://msdn.microsoft.com/library/windows/hardware/ff543095)
</dt> <dt>

[**SCSI\_PNP\_REQUEST\_BLOCK**](scsi-pnp-request-block.md)
</dt> <dt>

[**STOR\_DEVICE\_CAPABILITIES\_EX**](stor-device-capabilities-ex.md)
</dt> </dl>

 

 

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20STOR_DEVICE_CAPABILITIES%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





