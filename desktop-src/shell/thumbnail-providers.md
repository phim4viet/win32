---
Description: Windows Vista makes greater use of file-specific thumbnail images than earlier versions of Windows.
title: Thumbnail Handlers
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Thumbnail Handlers

Windows Vista makes greater use of file-specific thumbnail images than earlier versions of Windows. Windows Vista uses them in all views, in dialogs, and for any file type that provides them. Other applications can consume your thumbnail as well. Thumbnail display has also changed. Now, a continuous spectrum of user-selectable sizes is available rather than the discrete sizes such as Icons and Thumbnails provided in Windows XP.

> [!Note]  
> You might hear these thumbnails referred to as Live Icons.

 

Thumbnails of 32-bit resolution and as large as 256x256 pixels are often used in Windows Vista UI. File format owners should be prepared to display their thumbnails at that size. They should also provide non-static images for their thumbnails that reflect the particular file's contents. For example, a text file's thumbnail should show a miniature version of the document, including its text.

The [**IThumbnailProvider**](/windows/win32/Thumbcache/nn-thumbcache-ithumbnailprovider?branch=master) interface has been introduced to make providing a thumbnail easier and more straightforward than in the past, when [**IExtractImage**](/windows/win32/shobjidl_core/nn-shobjidl_core-iextractimage?branch=master) would have been used instead. Note, that existing code that uses **IExtractImage** is still valid under Windows Vista. However, **IExtractImage** is not supported in the **Details** pane.

This topic discusses the following:

-   [Thumbnail Processes](#thumbnail-processes)
-   [Thumbnail Cache and Sizing](#thumbnail-cache-and-sizing)
-   [Thumbnail Overlays](#thumbnail-overlays)
-   [Thumbnail Adornments](#thumbnail-adornments)
-   [Registering Your Thumbnail Handler](#registering-your-thumbnail-handler)
-   [Related topics](#related-topics)

## Thumbnail Processes

Handlers, including thumbnail handlers, run by default in a separate process. You can force the handler to run in-process by passing a **NULL** value as the bind context in a call to [**IShellItem::BindToHandler**](/windows/win32/shobjidl_core/nf-shobjidl_core-ishellitem-bindtohandler?branch=master) as shown here:


```
IShellItem::BindToHandler(NULL, BHID_ThumbnailHandler,..)
```



You can also opt out of running out of process by default by setting the DisableProcessIsolation entry in the registry as shown in this example. The class identifier (CLSID) {E357FCCD-A995-4576-B01F-234630154E96} is the CLSID for [**IThumbnailProvider**](/windows/win32/Thumbcache/nn-thumbcache-ithumbnailprovider?branch=master) implementations.

```
HKEY_CLASSES_ROOT
   CLSID
      {E357FCCD-A995-4576-B01F-234630154E96}
         DisableProcessIsolation = 1
```

## Thumbnail Cache and Sizing

When a thumbnail is needed, Windows first checks the thumbnail cache for the image. The thumbnail extractor is called if the image is not found in the cache. It is also called when the last modified time of the image is later than that of the copy in the cache.

The thumbnail images in this cache are stored in a set of discrete sizes. All sizes are given in pixels.

-   32x32
-   96x96
-   256x256
-   1024x1024

> [!Note]  
> These values are subject to change. You code should not assume that any particular size will always be used.

 

If an image is not square, you should not pad it yourself. Windows is responsible for respecting the original aspect ratio and padding the image to a square size.

When an image of a particular size is asked for, unless an exact match is found, Windows Vista always retrieves the next largest image and scales it down to the requested size. An image is never scaled up in size as was the case in previous versions of Windows.

The following table gives some examples of the relationship between requested size and available size.



| Maximum Image Size You Provide | Size Requested by the Extractor | You Provide                                 |
|--------------------------------|---------------------------------|---------------------------------------------|
| 156x120                        | 256x256                         | 156x120 (Do not pad, maintain aspect ratio) |
| 2048x1024                      | 256x256                         | 256x128 (Do not pad, maintain aspect ratio) |



 

You can declare a cutoff point as part of the file association entry in the registry. Below this size, thumbnails are not used.

```
HKEY_CLASSES_ROOT
   .fileextension
      ThumbnailCutoff
```

The ThumbnailCutoff entry is one of these REG\_DWORD values.



| Value | Cutoff | HighDPI Sensitive |
|-------|--------|-------------------|
| 0     | 32x32  | Yes               |
| 1     | 16x16  | Yes               |
| 2     | 48x48  | Yes               |
| 3     | 16x16  | Yes               |



 

High dots per inch (dpi) sensitivity means that the pixel dimensions of the thumbnail automatically adjust for the greater dpi. For instance, a 32x32 image at 96 dpi would be a 40x40 image at 120 dpi.

If the ThumbnailCutoff entry is not specified, the default cutoff is 20x20 (not dpi-sensitive).

## Thumbnail Overlays

Thumbnail overlays, a small image displayed over the lower right corner of the thumbnail, provide an opportunity for developers to apply brand identification to their thumbnails. Overlays are declared in the registry as part of the file association entry as shown here:

```
HKEY_CLASSES_ROOT
   .fileextension
      TypeOverlay
```

The TypeOverlay entry contains a REG\_SZ value interpreted as follows:

-   If the value is a resource reference, such as `ISVComponent.dll@,-155`, that image is used as the overlay for files with that file name extension.
-   If the value is an empty string, no overlay is applied to the image.
-   If the value is not present, the default icon of the associated application is used.

Overlays for your thumbnails should only be provided through this mechanism and applied by Windows. Do not apply overlays yourself.

## Thumbnail Adornments

Adornments such as drop shadows are applied to thumbnails based on the user's currently selected theme. Adornments are provided by Windows; do not create them yourself. Windows could change the look of particular adornments at any time, so if you provided you own you would risk falling out of synch with the system. Your thumbnails could wind up looking dated or out of place.

Potential adornments are declared in the registry as part of the file association entry as shown here:

```
HKEY_CLASSES_ROOT
   .fileextension
      Treatment
```

The Treatment entry contains one of these REG\_DWORD values:



| Value | Meaning         |
|-------|-----------------|
| 0     | No Adornment    |
| 1     | Drop Shadow     |
| 2     | Photo Border    |
| 3     | Video Sprockets |



 

A drop shadow is applied to images by default.

## Registering Your Thumbnail Handler

Registration of a thumbnail handler is based on standard file associations.

The GUID for the thumbnail handler Shell extension is `E357FCCD-A995-4576-B01F-234630154E96`.

## Related topics

<dl> <dt>

[**IThumbnailProvider**](/windows/win32/Thumbcache/nn-thumbcache-ithumbnailprovider?branch=master)
</dt> <dt>

[Building Thumbnail Handlers](building-thumbnail-providers.md)
</dt> <dt>

[Thumbnail Handler Guidelines](thumbnail-provider-guidelines.md)
</dt> </dl>

 

 


