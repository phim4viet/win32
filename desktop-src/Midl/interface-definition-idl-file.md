---
title: Interface Definition (IDL) File
description: By convention, the file that contains interface and type library definitions is called an IDL file, and has an .idl file name extension.
ms.assetid: 4df87df8-3206-4845-b5ab-d77ea443b9e3
keywords:
- interfaces MIDL , IDL file
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Interface Definition (IDL) File

By convention, the file that contains interface and type library definitions is called an IDL file, and has an .idl file name extension. In reality, the MIDL compiler will parse an interface definition file regardless of its extension. An interface is identified by the keyword [**interface**](interface.md).

Each interface consists of a header and a body. The interface header contains attributes that apply to the entire interface. The body of the interface contains the remaining interface definitions. For an overview of interfaces and IDL files, see [The Interface Definition Language (IDL) File](https://msdn.microsoft.com/library/windows/desktop/aa378712). For a summary of attributes that can be used in an interface header, see [IDL Attributes](idl-attributes.md).

 

 



