---
title: IAgentCommands GetVoice
description: IAgentCommands GetVoice
ms.assetid: ef8983bc-c70c-48c7-9c5f-1dae61028d90
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# IAgentCommands::GetVoice

\[Microsoft Agent is deprecated as of Windows 7, and may be unavailable in subsequent versions of Windows.\]

``` syntax
HRESULT GetVoice(
   BSTR * pbszVoice  // address of Voice setting for Commands collection
);
```

Retrieves the value of the [**Voice**](voice-property.md) property for a [**Commands**](https://msdn.microsoft.com/library/windows/desktop/ms695971) collection.

-   Returns S\_OK to indicate the operation was successful.

<dl> <dt>

<span id="pbszVoice"></span><span id="pbszvoice"></span><span id="PBSZVOICE"></span>*pbszVoice*
</dt> <dd>

The address of a BSTR that receives the value of the [**Voice**](voice-property.md) text setting for a [**Commands**](https://msdn.microsoft.com/library/windows/desktop/ms695971) collection.

</dd> </dl>

## See Also

[**IAgentCommands::SetVoice**](iagentcommands--setvoice.md), [**IAgentCommands::GetCaption**](iagentcommands--getcaption.md), [**IAgentCommands::GetVisible**](iagentcommands--getvisible.md)


 

 



