---
title: Using MSMQ as an RPC Transport
description: The RPC subsystem supports using MSMQ as a transport in synchronous and asynchronous modes.
ms.assetid: c3f96a91-b7bb-4c2a-8699-2100324af165
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Using MSMQ as an RPC Transport

The RPC subsystem supports using MSMQ as a transport in synchronous and asynchronous modes.

Synchronous mode uses conventional remote procedure calls. These calls use well-known endpoints and the message queue transport, [ncadg\_mq](https://msdn.microsoft.com/library/windows/desktop/aa367114), as the transport protocol. In synchronous mode, your remote procedures can have \[ [in](https://msdn.microsoft.com/library/windows/desktop/aa367051)\] and \[ [out](https://msdn.microsoft.com/library/windows/desktop/aa367136)\] parameters and can use the standard RPC security services. The RPC subsystem creates a reply queue for remote calls containing **\[out\]** parameters. The synchronous mode is useful for applications where the client needs to receive data from the server. The main limitation of this mode is that, as with conventional remote procedure calls, both the client and server must be running and remain running for the duration of the call.

Asynchronous mode lets client applications make calls to the server and return immediately, regardless of the state of the server application or the server computer. It also makes a subset of MSMQ features available for managing message queues and information flow. The [**RpcBindingSetOption**](/windows/win32/Rpcdce/nf-rpcdce-rpcbindingsetoption?branch=master) function lets you control quality of service, call priority, journaling, security, and the lifetime of the server process queue. The [**RpcServerUseProtseqEpEx**](/windows/win32/Rpcdce/nf-rpcdce-rpcserveruseprotseqepex?branch=master) function lets you specify attributes of the server process queue, such as queue persistence, authentication, and encryption.

You implement asynchronous MSMQ as you would synchronous MSMQ. You must use well-known endpoints, and define the transport protocol to be [ncadg\_mq](https://msdn.microsoft.com/library/windows/desktop/aa367114). In your IDL file, apply the [message](https://msdn.microsoft.com/library/windows/desktop/aa367077) attribute to the functions that use asynchronous message queuing. Note that message functions can have \[in\] parameters only.

 

 



