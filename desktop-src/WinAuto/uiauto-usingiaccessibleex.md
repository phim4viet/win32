---
title: Adding UI Automation Functionality to Active Accessibility Servers
description: Controls that do not have a Microsoft UI Automation provider but that implement IAccessible can easily be upgraded to provide some UI Automation functionality, by implementing the IAccessibleEx interface.
ms.assetid: 7ceab704-3e02-4550-b236-748e4f0a092a
keywords:
- UI Automation,Active Accessibility servers
- UI Automation,Microsoft Active Accessibility servers
- UI Automation,IAccessible
- UI Automation,IAccessibleEx
- UI Automation,exposing IAccessibleEx
- UI Automation,implementing IAccessibleEx
- IAccessible
- IAccessibleEx
- Microsoft Active Accessibility
- Active Accessibility
- exposing IAccessibleEx
- implementing IAccessibleEx
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Adding UI Automation Functionality to Active Accessibility Servers

Controls that do not have a Microsoft UI Automation provider but that implement [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master) can easily be upgraded to provide some UI Automation functionality, by implementing the [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) interface. This interface enables the control to expose UI Automation properties and control patterns, without the need for a full implementation of UI Automation provider interfaces such as [**IRawElementProviderFragment**](/windows/win32/UIAutomationCore/nn-uiautomationcore-irawelementproviderfragment?branch=master). To implement **IAccessibleEx**, the baseline Microsoft Active Accessibility object hierarchy must contain no errors or inconsistencies (such as a child object whose parent object does not list it as a child), and must not conflict with UI Automation specifications. If the Microsoft Active Accessibility object hierarchy meets these requirements, it is a good candidate for adding functionality by using **IAccessibleEx**; otherwise, you must implement UI Automation alone or alongside the Microsoft Active Accessibility implementation.

Take the case of a custom control that has a range value. The Microsoft Active Accessibility server for the control defines its role, and is able to return its current value, but lacks the means to return the minimum and maximum values of the control, because these properties are not defined in Microsoft Active Accessibility. A UI Automation client is able to retrieve the control's role, current value, and other Microsoft Active Accessibility properties, because the UI Automation core can obtain these through [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master). However, without access to an [**IRangeValueProvider**](/windows/win32/UIAutomationCore/nn-uiautomationcore-irangevalueprovider?branch=master) interface on the object, UI Automation is also unable to retrieve the maximum and minimum values.

The control developer could supply a complete UI Automation provider for the control, but this would mean duplicating much of the existing functionality of the [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master) implementation: for example, navigation and common properties. Instead, the developer can continue to rely on **IAccessible** to supply this functionality, while adding support for control-specific properties through [**IRangeValueProvider**](/windows/win32/UIAutomationCore/nn-uiautomationcore-irangevalueprovider?branch=master).

Updating the custom control requires these main steps:

-   Implement [IServiceProvider](http://go.microsoft.com/fwlink/p/?linkid=178086) on the accessible object so that the [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) interface can be found on this or a separate object.
-   Implement [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) on the accessible object.
-   Create distinct accessible objects for any Microsoft Active Accessibility child items, which in Microsoft Active Accessibility might have been represented by the [**IAccessible**](/windows/win32/oleacc/nn-oleacc-iaccessible?branch=master) interface on the parent object (for example, list items). Implement [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) on these objects.
-   Implement [**IRawElementProviderSimple**](/windows/win32/UIAutomationCore/nn-uiautomationcore-irawelementprovidersimple?branch=master) on all the accessible objects.
-   Implement the appropriate control pattern interfaces on the accessible objects.

This topic contains the following sections.

-   [Exposing IAccessibleEx](#exposing-iaccessibleex)
-   [Implementing IAccessibleEx](#implementing-iaccessibleex)
-   [Related topics](#related-topics)

## Exposing IAccessibleEx

Because the implementation of [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) for a control may reside in a separate object, client applications cannot rely on [**QueryInterface**](https://msdn.microsoft.com/library/windows/desktop/ms682521) to obtain this interface. Instead, clients are expected to call [**IServiceProvider::QueryService**](_inet_IServiceProvider_QueryService_Method). In the following example implementation of this method, it is assumed that **IAccessibleEx** is not implemented on a separate object; therefore the method simply calls through to **QueryInterface**.


```C++
HRESULT CListboxAccessibleObject::QueryService(REFGUID guidService, REFIID riid, LPVOID *ppvObject)
{
    if (!ppvObject)
    {
        return E_INVALIDARG;
    }
    *ppvObject = NULL;
    if (guidService == __uuidof(IAccessibleEx))
    {
        return QueryInterface(riid, ppvObject);
    }
    else 
    {
        return E_INVALIDARG;
    }
};
```



## Implementing IAccessibleEx

The method of [**IAccessibleEx**](/windows/win32/UIAutomationCore/nn-uiautomationcore-iaccessibleex?branch=master) that is of most interest is [**GetObjectForChild**](/windows/win32/UIAutomationCore/nf-uiautomationcore-iaccessibleex-getobjectforchild?branch=master). This method gives the Microsoft Active Accessibility server an opportunity to create an accessible object (one that exposes, at a minimum, **IAccessibleEx**) for a child item. In Microsoft Active Accessibility, child items typically are not represented as accessible objects but as children of an accessible object. However, because UI Automation requires that each element be represented by a separate accessible object, **GetObjectForChild** must create a separate object for each child on demand.

The following example implementation returns an accessible object for an item in a custom list view.


```C++
HRESULT CListboxAccessibleObject::GetObjectForChild(long idChild, IAccessibleEx **pRetVal)
{ 
    *pRetVal = NULL;
    VARIANT vChild;
    vChild.vt = VT_I4;
    vChild.lVal = idChild;

    // ValidateChildId is an application-defined function that checks whether
    // the child ID is valid. This is similar to code that validates the varChild
    // parameter in IAccessible methods.
    //
    // Additionally, if this idChild corresponds to a child that has its own
    // IAccessible, we should also return E_INVALIDARG here. (The caller
    // should instead be using the IAccessibleEx from that child's own
    // IAccessible in that case.)
    if (idChild == CHILDID_SELF || FAILED(ValidateChildId(vChild)))
    {
        return E_INVALIDARG;
    }

    // Return a suitable provider for this specific child.
    // This implementation returns a new instance each time; an implementation
    // can cache these if desired.

    // _pListboxControl is a member variable pointer to the owning control.
    IAccessibleEx* pAccEx  = new CListItemAccessibleObject(idChild, _pListboxControl);
    if (pAccEx == NULL)
    {
        return E_OUTOFMEMORY;
    }
    *pRetVal = pAccEx;
    return S_OK; 
}
```



For a complete sample implementation, see [Making Custom Controls Accessible, Part 5: Using IAccessibleEx to Add UI Automation Support to a Custom Control](http://go.microsoft.com/fwlink/p/?linkid=201075) on MSDN.

## Related topics

<dl> <dt>

[UI Automation Provider Programmer's Guide](uiauto-providerportal.md)
</dt> </dl>

 

 



