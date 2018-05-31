---
Description: The Media Foundation H.265 video decoder is a Media Foundation Transform that supports decoding H.265/HEVC content in Annex B format and can be used in playback of mp4 and m2ts files.
ms.assetid: BBE754E4-2AAD-4CFD-B53F-2B66693502EE
title: H.265 / HEVC Video Decoder
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# H.265 / HEVC Video Decoder

The Media Foundation H.265 video decoder is a [Media Foundation Transform](media-foundation-transforms.md) that supports decoding H.265/HEVC content in Annex B format and can be used in playback of mp4 and m2ts files.

The H.265 video decoder exposes the following interfaces.

-   [**ICodecAPI**](dshow.icodecapi) (supported in Windows 8)
-   [**IMFAttributes**](/windows/win32/mfobjects/nn-mfobjects-imfattributes?branch=master)
-   [**IMFGetService**](/windows/win32/mfidl/nn-mfidl-imfgetservice?branch=master)
-   [**IMFQualityAdvise**](/windows/win32/mfidl/nn-mfidl-imfqualityadvise?branch=master)
-   [**IMFQualityAdvise2**](/windows/win32/mfidl/nn-mfidl-imfqualityadvise2?branch=master)
-   [**IMFRateControl**](/windows/win32/mfidl/nn-mfidl-imfratecontrol?branch=master)
-   [**IMFRateSupport**](/windows/win32/mfidl/nn-mfidl-imfratesupport?branch=master)
-   [**IMFRealTimeClient**](/windows/win32/mfidl/nn-mfidl-imfrealtimeclient?branch=master)
-   [**IMFTransform**](/windows/win32/mftransform/nn-mftransform-imftransform?branch=master)

To create an instance of the decoder, do one of the following:

-   Call the [**MFTEnum**](/windows/win32/mfapi/nf-mfapi-mftenum?branch=master) or [**MFTEnumEx**](/windows/win32/mfapi/nf-mfapi-mftenumex?branch=master) function.
-   Call [**CoCreateInstance**](com.cocreateinstance). The CLSID for the decoder is **CLSID\_CMSH265EncoderMFT**, declared in wmcodecdsp.h.

## Input Types

The input type must contain at least the following two attributes:



| Attribute                                                 | Description                                                                                   |
|-----------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| [**MF\_MT\_MAJOR\_TYPE**](mf-mt-major-type-attribute.md) | **MFMediaType\_Video**                                                                        |
| [**MF\_MT\_SUBTYPE**](mf-mt-subtype-attribute.md)        | [MFVideoFormat\_HEVC](video-subtype-guids.md#encoded-video-types) or MFVideoFormat\_HEVC\_ES |



 

The first media subtype, MFVideoFormat\_HEVC, indicates that the media samples carry H.265 bitstream with start codes, and the stream has interleaved SPS/PPS. It assumes one frame per sample.

The media subtype MFVideoFormat\_ HEVC\_ES is to indicate the media samples carry elementary H.265 bitstream, where each sample may contain a partial picture, multiple pictures, some pictures plus a partial picture.

The input media types cannot change dynamically between two types. The decoder can detect in-flight output format changes based on the elementary stream syntax (aspect ratio, dimension, interlace flags, colorimetry information) and trigger corresponding output media type changes.

For input media type, the decoder expects the source to set the correct Profile. For example if the content is going to be 10bit, input media type should specify the profile as Main10.

## Output Types

The decoder supports the following output subtypes:

-   **MFVideoFormat\_NV12**
-   **MFVideoFormat\_P010**

For more information about these subtypes, see [Video Subtype GUIDs](video-subtype-guids.md).

## Transform Attributes

The H.265 decoder implements the [**IMFTransform::GetAttributes**](/windows/win32/mftransform/nf-mftransform-imftransform-getattributes?branch=master) method. Applications can use this method to get or set the following attributes.



| Attribute                                                                                       | Description                                                                                                                   |
|-------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| [CODECAPI\_AVLowLatencyMode](codecapi-avlowlatencymode.md)                                     | Enables or disables low-latency decoding mode.                                                                                |
| [CODECAPI\_AVDecNumWorkerThreads](codecapi-avdecnumworkerthreads.md)                           | Sets the number of worker threads used by the decoder.                                                                        |
| [CODECAPI\_AVDecVideoThumbnailGenerationMode](dshow.avdecvideothumbnailgenerationmode_property) | Enables or disables thumbnail generation mode.                                                                                |
| [MF\_NALU\_LENGTH\_SET](mf-nalu-length-set.md)                                                 | Indicates that NALU length information will be sent as a BLOB with each compressed H.265 sample.                              |
| [MF\_NALU\_LENGTH\_INFORMATION](mf-nalu-length-information.md)                                 | Indicates the lengths of NALUs in the sample. This is a MF BLOB that is set on compressed input samples to the H.265 decoder. |
| [MF\_SA\_MINIMUM\_OUTPUT\_SAMPLE\_COUNT](mf-sa-minimum-output-sample-count.md)                 | Specifies the maximum number of output samples.                                                                               |



 

The H.265 decoder supports the [**ICodecAPI**](dshow.icodecapi) interface. This interface provides an alternativate API for setting the following codec properties.

-   [CODECAPI\_AVDecNumWorkerThreads](codecapi-avdecnumworkerthreads.md)
-   [CODECAPI\_AVDecVideoThumbnailGenerationMode](dshow.avdecvideothumbnailgenerationmode_property)
-   [CODECAPI\_AVLowLatencyMode](codecapi-avlowlatencymode.md)

## Format Constraints

The decoder supports the following formats:



|                    |                                                                                                                                                                                                                                                                      |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Profiles/Levels    | Main, Main Still Picture, and Main10 profiles                                                                                                                                                                                                                        |
| Chroma Formats     | 4:2:0 chroma                                                                                                                                                                                                                                                         |
| Minimum Resolution | 48 × 48 pixels                                                                                                                                                                                                                                                       |
| Maximum Resolution | 4096 × 2304 pixels<br/> The maximum guaranteed resolution for DXVA acceleration is 1920 × 1088 pixels; at higher resolutions, decoding is done with DXVA, if it is supported by the underlying hardware, otherwise, decoding is done with software.<br/> |
| DXVA               | The decoder supports DXVA version 2, but not DXVA version 1.                                                                                                                                                                                                         |



 

Input data must conform to Annex B of ITU-T H.265 \| ISO/IEC 23008-2. The data must include the start codes. The decoder skips bytes until it finds a valid sequence parameter set (SPS) and picture parameter set (PPS) in the byte stream.

## Requirements



|                                     |                                                                                          |
|-------------------------------------|------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 10 \[desktop apps only\]<br/>                                              |
| Minimum supported server<br/> | None supported<br/>                                                                |
| DLL<br/>                      | <dl> <dt>Mshevcdec.dll</dt> </dl> |



## See also

<dl> <dt>

[Codec Objects](codecobjects.md)
</dt> </dl>

 

 



