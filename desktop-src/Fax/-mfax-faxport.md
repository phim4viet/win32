---
Description: The FaxPort object permits a fax client application to retrieve and set configuration information for a fax port on a connected fax server.
ms.assetid: cc59452b-194e-4a68-955b-ac39cd5325ff
title: FaxPort
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# FaxPort

The FaxPort object permits a fax client application to retrieve and set configuration information for a fax port on a connected fax server. Use the FaxPort object to create a [FaxStatus](-mfax-faxstatus.md) object for a fax port and to create a [FaxRoutingMethods](-mfax-faxroutingmethods.md) object to enumerate the fax routing methods associated with a port.

A FaxPort object is created by a [FaxPorts](-mfax-faxports.md) object. FaxStatus objects and FaxRoutingMethods objects are created by FaxPort objects.

A fax client application must create an instance of a [FaxServer](-mfax-faxserver-client.md) object before accessing most other objects that begin with Fax. (A fax server connection is not required to access a [FaxTiff](-mfax-faxtiff.md) object.)

## C/C++

-   Create by calling the [**IFaxPorts::get\_Item**](/windows/previous-versions/Faxcom/nf-faxcom-ifaxports-get_item?branch=master) method.
-   Supports the [**IFaxPort**](/windows/previous-versions/Faxcom/nn-faxcom-ifaxport?branch=master) interface.

For more information about creating an instance of a FaxPort object, and for a list of the object's properties and methods, see [**IFaxPort**](/windows/previous-versions/Faxcom/nn-faxcom-ifaxport?branch=master).

## Visual Basic

Create by retrieving the [**Item**](-mfax-faxports-object-visual-basic-.md) property of the [**FaxPorts**](-mfax-faxports-object-visual-basic-.md) collection.

For more information about creating a FaxPort object, and for a list of the properties and methods of the object, see [**FaxPort object (Visual Basic)**](-mfax-faxport-object-visual-basic-.md).

 

 


