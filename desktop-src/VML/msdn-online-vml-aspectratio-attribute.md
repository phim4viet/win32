---
title: VML AspectRatio Attribute
description: VML AspectRatio Attribute
ms.assetid: bc209218-9259-454e-bad2-58f67e211709
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# VML AspectRatio Attribute

This topic describes VML, a feature that is deprecated as of Windows Internet Explorer 9. Webpages and applications that rely on VML should be [migrated to SVG](http://go.microsoft.com/fwlink/p/?LinkID=236964) or other widely supported standards.

> [!Note]  
> As of December 2011, this topic has been archived. As a result, it is no longer actively maintained. For more information, see [Archived Content](https://msdn.microsoft.com/library/hh772377). For information, recommendations, and guidance regarding the current version of Windows Internet Explorer, see [Internet Explorer Developer Center](http://go.microsoft.com/fwlink/p/?linkid=204313).

 

Determines whether the aspect ratio of a shape can be changed by an editor. Read/write. **VgTriState**.

**Applies To**

[Locks](msdn-online-vml-locks-element.md)

**Tag Syntax**

&lt;o: *element* aspectratio=" *expression* "&gt;

**Remarks**

If **True**, the aspect ratio of a shape cannot be changed by an editor. This has the effect of locking the corner resize handles so that shapes can only be resized isotropically. The default is **False**.

*Microsoft Office Extensions Attribute*

 

 



