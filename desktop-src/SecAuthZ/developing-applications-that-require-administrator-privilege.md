---
Description: It is possible to develop an application that performs operations that require administrator privilege yet runs as a standard user.
ms.assetid: 78099b59-b09b-43c0-91f5-adb5c9e0e191
title: Developing Applications that Require Administrator Privilege
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Developing Applications that Require Administrator Privilege

It is possible to develop an application that performs operations that require administrator privilege yet runs as a standard user.

There are several models for accomplishing this.



| Topic                                                                | Description                                                                                                                                                                                          |
|----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Elevated Task Model](elevated-task-model.md)                       | An application running as a standard user performs operations that require administrator privilege by starting a scheduled task.                                                                     |
| [Operating System Service Model](operating-system-service-model.md) | An application running as a standard user communicates with a service running as **SYSTEM** by using [Remote Procedure Call](https://msdn.microsoft.com/library/windows/desktop/aa378651) (RPC).                                              |
| [Administrator Broker Model](administrator-broker-model.md)         | The application is divided into two programs. One of the programs runs as a standard user, and the other runs with administrator privilege.                                                          |
| [Administrator COM Object Model](administrator-com-object-model.md) | An application running as a standard user performs operations that require administrator privilege by creating an elevated [Component Object Model](https://msdn.microsoft.com/library/windows/desktop/ms680573) object. |



 

 

 


