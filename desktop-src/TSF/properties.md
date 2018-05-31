---
title: Properties
description: Text Services Framework (TSF) provides properties that associate metadata with a range of text.
ms.assetid: 99d8564f-98bc-4f30-bff9-923a4016a5fe
keywords:
- Text Services Framework (TSF),properties
- TSF (Text Services Framework),properties
- text services,properties
- TSF-enabled applications,properties
- properties
- Text Services Framework (TSF),property types
- TSF (Text Services Framework),property types
- text services,property types
- TSF-enabled applications,property types
- property types
- Text Services Framework (TSF),persistent storage of properties
- TSF (Text Services Framework),persistent storage of properties
- text services,persistent storage of properties
- TSF-enabled applications,persistent storage of properties
- persistent storage of properties
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Properties

Text Services Framework (TSF) provides properties that associate metadata with a range of text. These properties include, but are not limited to, display attributes such as bold text, the language identifier of the text, and raw data provided by a text service such as the audio data associated with text from the speech text service.

The following example demonstrates how a hypothetical text color property with possible values of red (R), green (G), or blue (B) can be viewed.


```C++
COLOR:      RR      GGGGGGGG
TEXT:  this is some colored text
```



Properties of different types can overlap. For example, take the previous example and add a text attribute that can be either bold (B) or italic (I).


```C++
ATTRIB:BBBBBBB      IIIIIIIIIIII
COLOR:      RR      GGGGGGGG
TEXT:  this is some colored text
```



The text "this" would be bold, "is" would be both bold and red, "some" would be displayed normally, "colored" would be green and italicized and "text" would be italicized.

Properties of the same type cannot overlap. For example, the following situation is not allowed because "is" and "colored" have overlapping values of the same types.


```C++
COLOR: GGG GGGG RRR BBBBGGG     
COLOR:      RR      GGGGGGGG
TEXT:  this is some colored text
```



## Property Types

TSF defines three different types of properties.



|                |                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Static         | A static property object stores the property data with text. It also stores the range of text information for each range that the property applies to. ITfReadOnlyProperty::GetType returns the GUID\_TFCAT\_PROPSTYLE\_STATIC category.                                                                                                                                                                                                                      |
| Static-Compact | A static-compact property object is identical to a static property object except a static-compact property does not store range data. When the range covered by a static-compact property is requested, a range is created for each group of adjacent properties. Static-compact properties are the most efficient way to store properties on a per-character basis. ITfReadOnlyProperty::GetType returns the GUID\_TFCAT\_PROPSTYLE\_STATICCOMPACT category. |
| Custom         | A custom property object stores the range information for each range that the property applies to. It does not, however, store the actual data for the property. Instead, a custom property stores an ITfPropertyStore object. The TSF manager uses this object to access and maintain the property data.ITfReadOnlyProperty::GetType returns the GUID\_TFCAT\_PROPSTYLE\_CUSTOM category.                                                                    |



 

## Working with Properties

The property value and attributes are obtained using the [ITfReadOnlyProperty](https://msdn.microsoft.com/library/windows/desktop/ms628936) interface and modified using the [ITfProperty](/windows/win32/Msctf/nn-msctf-itfproperty?branch=master) interface.

If a specific property type is required, then [ITfContext::GetProperty](https://msdn.microsoft.com/library/windows/desktop/ms538791) is used. **ITfContext::GetProperty** requires a **GUID** that identifies the property to obtain. TSF defines a set of [predefined property identifiers](predefined-properties.md) used or a text service can define its own property identifiers. If a custom property is used, the property provider must publish the property **GUID** and the format of the data obtained.

For example, to obtain the **CLSID** for the owner of a range of text, call **ITfContext::GetProperty** to obtain the property object, call [ITfProperty::FindRange](https://msdn.microsoft.com/library/windows/desktop/ms628903) to obtain the range that entirely covers the property, then call [ITfReadOnlyProperty::GetValue](https://msdn.microsoft.com/library/windows/desktop/ms628940) to get a [TfGuidAtom](https://msdn.microsoft.com/library/windows/desktop/ms629052) that represents the **CLSID** of the text service that owns the text. The following example shows a function that, given a context, range and an edit cookie, will obtain the **CLSID** of the text service that owns the text.


```C++
HRESULT GetTextOwner(   ITfContext *pContext, 
                        ITfRange *pRange, 
                        TfEditCookie ec, 
                        CLSID *pclsidOwner)
{
    HRESULT     hr;
    ITfProperty *pProp;

    *pclsidOwner = GUID_NULL;

    hr = pContext->GetProperty(GUID_PROP_TEXTOWNER, &amp;pProp);
    if(S_OK == hr)
    {
        ITfRange    *pPropRange;

        hr = pProp->FindRange(ec, pRange, &amp;pPropRange, TF_ANCHOR_START);
        if(S_OK == hr)
        {
            VARIANT var;

            VariantInit(&amp;var);
            hr = pProp->GetValue(ec, pPropRange, &amp;var);
            if(S_OK == hr)
            {
                if(VT_I4 == var.vt)
                {
                    /*
                    var.lVal is a TfGuidAtom that represents the CLSID of the 
                    text owner. Use ITfCategoryMgr to obtain the CLSID from 
                    the TfGuidAtom.
                    */
                    ITfCategoryMgr  *pCatMgr;

                    hr = CoCreateInstance(  CLSID_TF_CategoryMgr,
                                            NULL, 
                                            CLSCTX_INPROC_SERVER, 
                                            IID_ITfCategoryMgr, 
                                            (LPVOID*)&amp;pCatMgr);
                    if(SUCCEEDED(hr))
                    {
                        hr = pCatMgr->GetGUID((TfGuidAtom)var.lVal, pclsidOwner);
                        if(SUCCEEDED(hr))
                        {
                            /*
                            *pclsidOwner now contains the CLSID of the text 
                            service that owns the text at the selection.
                            */
                        }

                        pCatMgr->Release();
                    }
                }
                else
                {
                    //Unrecognized VARIANT type 
                    hr = E_FAIL;
                }
                
                VariantClear(&amp;var);
            }
            
            pPropRange->Release();
        }
        
        pProp->Release();
    }

    return hr;
}

```



Properties can also be enumerated by obtaining an [IEnumTfProperties](https://msdn.microsoft.com/library/windows/desktop/ms538218) interface from [ITfContext::EnumProperties](https://msdn.microsoft.com/library/windows/desktop/ms538785).

## Persistent Storage of Properties

Often, properties are transparent to an application and are used by one or more text services. In order to preserve the property data, such as when saving to a file, an application must serialize the property data when it is stored and unserialize the property data when the data is restored. In this case, the application should not be interested in individual properties, but should enumerate all properties in the context and store them.

When storing property data, an application should perform the following steps.

1.  Obtain a property enumerator by calling **ITfContext::EnumProperties**.
2.  Enumerate each property by calling [IEnumTfProperties::Next](https://msdn.microsoft.com/library/windows/desktop/ms538224).
3.  For each property, obtain a range enumerator by calling [ITfReadOnlyProperty::EnumRanges](https://msdn.microsoft.com/library/windows/desktop/ms628937).
4.  Enumerate each range in the property by calling [IEnumTfRanges::Next](https://msdn.microsoft.com/library/windows/desktop/ms538379).
5.  For each range in the property, call [ITextStoreACPServices::Serialize](https://msdn.microsoft.com/library/windows/desktop/ms538392) with the property, range, a [TF\_PERSISTENT\_PROPERTY\_HEADER\_ACP](https://msdn.microsoft.com/library/windows/desktop/ms629083) structure, and a stream object implemented by the application.
6.  Write the contents of the **TF\_PERSISTENT\_PROPERTY\_HEADER\_ACP** structure into persistent memory.
7.  Write the contents of the stream object into persistent memory.
8.  Continue the previous steps for all of the ranges in all of the properties.
9.  The application should write some type of terminiator into the stream so that, when the data is restored, a stopping point can be identified.


```C++
HRESULT SaveProperties( ITfContext *pContext, 
                        ITextStoreACPServices *pServices, 
                        TfEditCookie ec, 
                        IStream *pStream)
{
    HRESULT             hr;
    IEnumTfProperties   *pEnumProps;
    TF_PERSISTENT_PROPERTY_HEADER_ACP PropHeader;
    ULONG uWritten;
    
    //Enumerate the properties in the context. 
    hr = pContext->EnumProperties(&amp;pEnumProps);
    if(SUCCEEDED(hr))
    {
        ITfProperty *pProp;
        ULONG       uFetched;

        while(SUCCEEDED(pEnumProps->Next(1, &amp;pProp, &amp;uFetched)) &amp;&amp; uFetched)
        {
            //Enumerate all the ranges that contain the property. 
            IEnumTfRanges   *pEnumRanges;
            hr = pProp->EnumRanges(ec, &amp;pEnumRanges, NULL);
            if(SUCCEEDED(hr))
            {
                IStream *pTempStream;

                //Create a temporary stream to write the property data to. 
                hr = CreateStreamOnHGlobal(NULL, TRUE, &amp;pTempStream);
                if(SUCCEEDED(hr))
                {
                    ITfRange    *pRange;

                    while(SUCCEEDED(pEnumRanges->Next(1, &amp;pRange, &amp;uFetched)) &amp;&amp; uFetched)
                    {
                        LARGE_INTEGER li;

                        //Reset the temporary stream pointer. 
                        li.QuadPart = 0;
                        pTempStream->Seek(li, STREAM_SEEK_SET, NULL);
                        
                        //Get the property header and data for the range. 
                        hr = pServices->Serialize(pProp, pRange, &amp;PropHeader, pTempStream);

                        /*
                        Write the property header into the primary stream. 
                        The header also contains the size of the property 
                        data.
                        */
                        hr = pStream->Write(&amp;PropHeader, sizeof(PropHeader), &amp;uWritten);

                        //Reset the temporary stream pointer. 
                        li.QuadPart = 0;
                        pTempStream->Seek(li, STREAM_SEEK_SET, NULL);

                        //Copy the property data from the temporary stream into the primary stream. 
                        ULARGE_INTEGER  uli;
                        uli.QuadPart = PropHeader.cb;

                        hr = pTempStream->CopyTo(pStream, uli, NULL, NULL);

                        pRange->Release();
                    }
                    
                    pTempStream->Release();
                }
                
                pEnumRanges->Release();
            }
            
            pProp->Release();
        }
        
        pEnumProps->Release();
    }

    //Write a property header with zero size and guid into the stream as a terminator 
    ZeroMemory(&amp;PropHeader, sizeof(PropHeader));
    hr = pStream->Write(&amp;PropHeader, sizeof(PropHeader), &amp;uWritten);

    return hr;
}

```



**ITextStoreACPServices::Serialize**[ITfPropertyStore::Serialize](https://msdn.microsoft.com/library/windows/desktop/ms628900)

When restoring property data, an application should perform the following steps.

1.  Set the stream pointer to the start of the first **TF\_PERSISTENT\_PROPERTY\_HEADER\_ACP** structure.
2.  Read the **TF\_PERSISTENT\_PROPERTY\_HEADER\_ACP** structure.
3.  Call **ITfContext::GetProperty** with the **guidType** member of the **TF\_PERSISTENT\_PROPERTY\_HEADER\_ACP** structure.
4.  The application can do one of two things at this point.
    1.  Create an instance of an [ITfPersistentPropertyLoaderACP](https://msdn.microsoft.com/library/windows/desktop/ms628877) object that the application must implement. Then call [ITextStoreACPServices::Unserialize](https://msdn.microsoft.com/library/windows/desktop/ms538394) with **NULL** for *pStream* and the **ITfPersistentPropertyLoaderACP** pointer.
    2.  Pass the input stream to **ITextStoreACPServices::Unserialize** and **NULL** for *pLoader*.

    The first method is preferred as it is the most efficient. Implementing the second method causes all of the property data to be read from the stream during the **ITextStoreACPServices::Unserialize** call. The first method causes the property data to be read on demand at a later time.
5.  Repeat the previous steps until all property blocks are unserialized.


```C++
HRESULT LoadProperties( ITfContext *pContext, 
                        ITextStoreACPServices *pServices, 
                        IStream *pStream)
{
    HRESULT hr;
    ULONG   uRead;
    TF_PERSISTENT_PROPERTY_HEADER_ACP PropHeader;

    /*
    Read each property header and property data from the stream. The 
    list of properties is terminated by a TF_PERSISTENT_PROPERTY_HEADER_ACP 
    structure with a cb member of zero.
    */
    hr = pStream->Read(&amp;PropHeader, sizeof(PropHeader), &amp;uRead);
    while(  SUCCEEDED(hr) &amp;&amp; 
            (sizeof(PropHeader) == uRead) &amp;&amp; 
            (0 != PropHeader.cb))
    {
        ITfProperty *pProp;

        hr = pContext->GetProperty(PropHeader.guidType, &amp;pProp);
        if(SUCCEEDED(hr))
        {
            /*
            Have TSF read the property data from the stream. This call 
            requests a read-only lock, so be sure it can be granted 
            or else this method will fail.
            */
            CTSFPersistentPropertyLoader *pLoader = new CTSFPersistentPropertyLoader(&amp;PropHeader, pStream);
            hr = pServices->Unserialize(pProp, &amp;PropHeader, NULL, pLoader);

            pProp->Release();
        }

        //Read the next header. 
        hr = pStream->Read(&amp;PropHeader, sizeof(PropHeader), &amp;uRead);
    }

    return hr;
}

```



 

 



