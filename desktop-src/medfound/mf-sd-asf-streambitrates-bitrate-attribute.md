---
Description: Specifies the average bit rate, in bits per second, of a stream in an Advanced Systems Format (ASF) file. This attribute corresponds to the Stream Bitrate Properties Object defined in the ASF specification.
ms.assetid: 7ec6004f-c71b-413f-b2fd-dc03a5bf8c57
title: MF\_SD\_ASF\_STREAMBITRATES\_BITRATE attribute
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# MF\_SD\_ASF\_STREAMBITRATES\_BITRATE attribute

Specifies the average bit rate, in bits per second, of a stream in an Advanced Systems Format (ASF) file. This attribute corresponds to the Stream Bitrate Properties Object defined in the ASF specification.

## Data type

**UINT32**

## Remarks

The [**IMFASFContentInfo::GeneratePresentationDescriptor**](/windows/win32/wmcontainer/nf-wmcontainer-imfasfcontentinfo-generatepresentationdescriptor?branch=master) method generates this attribute and sets it on the stream descriptor. The application can create the stream descriptor for the stream from the presentation descriptor by calling [**IMFPresentationDescriptor::GetStreamDescriptorByIndex**](/windows/win32/mfidl/nf-mfidl-imfpresentationdescriptor-getstreamdescriptorbyindex?branch=master).

The attribute value equals the Average Bit Rate field in the Stream Bit Rate Properties object.

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                           |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                     |
| Header<br/>                   | <dl> <dt>Wmcontainer.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[**IMFAttributes::GetUINT32**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-getuint32?branch=master)
</dt> <dt>

[**IMFAttributes::SetUINT32**](/windows/win32/mfobjects/nf-mfobjects-imfattributes-setuint32?branch=master)
</dt> <dt>

[**IMFStreamDescriptor**](/windows/win32/mfidl/nn-mfidl-imfstreamdescriptor?branch=master)
</dt> <dt>

[Stream Descriptor Attributes](stream-descriptor-attributes.md)
</dt> <dt>

[ASF Header Object](asf-file-structure.md#header-object)
</dt> </dl>

 

 



