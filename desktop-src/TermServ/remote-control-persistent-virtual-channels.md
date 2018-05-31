---
title: Remote Control Persistent Virtual Channels
description: A remote control persistent virtual channel is not closed when a remote control connects or disconnects for the session connected to the client. Data will continue to be transmitted and received through this channel.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\markl
ms.assetid: 0c3d5429-250e-4272-8cdd-69097acfaff4
ms.prod: windows-server-dev
ms.technology: remote-desktop-services
ms.tgt_platform: multiple
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
---

# Remote Control Persistent Virtual Channels

On Windows XP, a DLL can specify one or more virtual channels as *remote control persistent*. A remote control persistent virtual channel is not closed when a remote control connects or disconnects for the session connected to the client. Data will continue to be transmitted and received through this channel. Virtual channels that the DLL does not specify as remote control persistent will close in this scenario.

Remote control persistent virtual channels are specified during the call to **VirtualChannelInit**. Refer to the reference page for [**VirtualChannelInit**](/windows/win32/Cchannel/nc-cchannel-virtualchannelinit?branch=master) for specific information about this.

 

 



