---
Description: The Win32\_COMApplicationClasses abstract association WMI class relates a Component Object Model (COM) component and the COM application where it resides.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 7c188199-86fb-45ba-b318-9d9529b831b8
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: Win32\_COMApplicationClasses class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Win32\_COMApplicationClasses class

The **Win32\_COMApplicationClasses** abstract association [WMI class](https://msdn.microsoft.com/library/aa393244) relates a Component Object Model (COM) component and the COM application where it resides.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[abstract, UUID("{0F73ED51-8ED9-11d2-B340-00105A1F8569}"), AMENDMENT]
class Win32_COMApplicationClasses : CIM_Component
{
  Win32_COMClass       REF PartComponent;
  Win32_COMApplication REF GroupComponent;
};
```

## Members

The **Win32\_COMApplicationClasses** class has these types of members:

-   [Properties](#properties)

### Properties

The **Win32\_COMApplicationClasses** class has these properties.

<dl> <dt>

**GroupComponent**
</dt> <dd> <dl> <dt>

Data type: **Win32\_COMApplication**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Override**](https://msdn.microsoft.com/library/aa393650) ("GroupComponent"), [**MappingStrings**](https://msdn.microsoft.com/library/aa393650) ("WMI\|Win32\_COMApplication")
</dt> </dl>

A [**Win32\_COMApplication**](win32-comapplication.md) that represents the COM application containing the COM component.

</dd> <dt>

**PartComponent**
</dt> <dd> <dl> <dt>

Data type: **Win32\_COMClass**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Override**](https://msdn.microsoft.com/library/aa393650) ("PartComponent"), [**MappingStrings**](https://msdn.microsoft.com/library/aa393650) ("WMI\|Win32\_COMClass")
</dt> </dl>

A [**Win32\_COMClass**](win32-comclass.md) that represents the COM component grouped under the COM application.

</dd> </dl>

## Remarks

The **Win32\_COMApplicationClasses** class is derived from [**CIM\_Component**](cim-component.md).

## Requirements



|                                     |                                                                                         |
|-------------------------------------|-----------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista<br/>                                                                |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                          |
| Namespace<br/>                | Root\\CIMV2<br/>                                                                  |
| MOF<br/>                      | <dl> <dt>CIMWin32.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>CIMWin32.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_Component**](cim-component.md)
</dt> <dt>

[Operating System Classes](https://msdn.microsoft.com/library/aa392727)
</dt> </dl>

 

 



