---
Description: The Win32\_ClientApplicationSetting association WMI class relates an executable file and a Component Object Model (COM) application that contains the COM configuration options for the executable file.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: c43d80ee-0f29-4452-b51f-f18543bc1d35
ms.prod: windows-server-dev
ms.technology:
- cimwin32
- windows-management-instrumentation
ms.tgt_platform: multiple
title: Win32\_ClientApplicationSetting class
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Win32\_ClientApplicationSetting class

The **Win32\_ClientApplicationSetting** association [WMI class](https://msdn.microsoft.com/library/aa393244) relates an executable file and a Component Object Model (COM) application that contains the COM configuration options for the executable file.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties. Properties are listed in alphabetic order, not MOF order.

## Syntax

``` syntax
[Association, Dynamic, Provider("CIMWin32"), UUID("{0F73ED5E-8ED9-11d2-B340-00105A1F8569}"), AMENDMENT]
class Win32_ClientApplicationSetting
{
  Win32_DCOMApplication REF Application;
  CIM_DataFile          REF Client;
};
```

## Members

The **Win32\_ClientApplicationSetting** class has these types of members:

-   [Properties](#properties)

### Properties

The **Win32\_ClientApplicationSetting** class has these properties.

<dl> <dt>

**Application**
</dt> <dd> <dl> <dt>

Data type: **Win32\_DCOMApplication**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**MappingStrings**](https://msdn.microsoft.com/library/aa393650) ("WMI\|Win32\_DCOMApplication")
</dt> </dl>

Reference to the instance that represents the COM application that contains configuration options of the executable file.

</dd> <dt>

**Client**
</dt> <dd> <dl> <dt>

Data type: **CIM\_DataFile**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**MappingStrings**](https://msdn.microsoft.com/library/aa393650) ("CIM\|CIM\_DataFile")
</dt> </dl>

Reference to the instance that represents the executable file that uses COM settings.

</dd> </dl>

## Remarks

**Win32\_ClientApplicationSetting** does not support enumeration.

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

[Operating System Classes](https://msdn.microsoft.com/library/aa392727)
</dt> </dl>

 

 



