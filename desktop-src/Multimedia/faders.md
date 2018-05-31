---
title: Faders
description: Faders
ms.assetid: 2ca6be9f-9825-44d9-99c1-abcf6f0b42f7
keywords:
- audio mixers,controls
- audio mixers,faders
- mixers,controls
- mixers,faders
- faders
- MIXERCONTROLDETAILS_UNSIGNED structure
- volume fade control
- bass volume fade control
- treble volume fade control
- graphic equalizer control
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Faders

The fader controls are typically vertical controls that can be adjusted up or down. These controls have a linear scale and use the [**MIXERCONTROLDETAILS\_UNSIGNED**](/windows/win32/mmeapi/?branch=master) structure to retrieve and set control details. The following table describes the types of faders.



| Control   | Description                                                                                                                                                                                                                                                                                                                                                                                                     |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Fader     | General fade control. The range of acceptable values is 0 through 65,535.                                                                                                                                                                                                                                                                                                                                       |
| Volume    | General volume fade control. The range of acceptable values is 0 through 65,535. For information about changing this range, see the documentation for your mixer device.                                                                                                                                                                                                                                        |
| Bass      | Bass volume fade control. The range of acceptable values is 0 through 65,535. The limits of the bass frequency band are hardware specific. For information about band limits, see the documentation for your mixer device.                                                                                                                                                                                      |
| Treble    | Treble volume fade control. The range of acceptable values is 0 through 65,535. The limits of the treble frequency band are hardware specific. For information about the band limits, see the documentation for your mixer device.                                                                                                                                                                              |
| Equalizer | Graphic equalizer control. The range of acceptable values for one band of the equalizer is 0 through 65,535. The number of equalizer bands and their limits are hardware specific. For information about the equalizer, see the documentation for your mixer device. You can use the [**MIXERCONTROLDETAILS\_LISTTEXT**](/windows/win32/mmeapi/?branch=master) structure to retrieve text labels for the equalizer. |



 

 

 



