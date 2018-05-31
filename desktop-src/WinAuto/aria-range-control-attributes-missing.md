---
title: ARIA Range Control Attributes Missing
description: ARIA Range Control Attributes Missing
ms.assetid: B79F6277-5339-406A-B5FC-A3657BFC5034
keywords:
- AriaRangeControlAttributesAbsentId
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# ARIA Range Control Attributes Missing

## Text

Element has **progressbar** or **slider** role but is not exposing corresponding **aria-valuemin** , **aria-valuemax** , and **aria-valuenow** attributes.

## Type

Error

## Description

This error applies to elements that have a [**role**](https://msdn.microsoft.com/library/windows/apps/hh780024) (implicit or explicit) that is equal to **progressbar**, **slider**, or **spinbutton**.

According to the Web Accessibility Initiative - Accessible Rich Internet Applications (WAI-ARIA) specification, elements that have the **progressbar**, **slider**, or **spinbutton** role must expose the [**aria-valuemax**](https://msdn.microsoft.com/library/windows/apps/hh465724), [**aria-valuemin**](https://msdn.microsoft.com/library/windows/apps/hh465726), and [**aria-valuenow**](https://msdn.microsoft.com/library/windows/apps/hh465728) attributes.

To fix this error, set the [**aria-valuemax**](https://msdn.microsoft.com/library/windows/apps/hh465724), [**aria-valuemin**](https://msdn.microsoft.com/library/windows/apps/hh465726), and [**aria-valuenow**](https://msdn.microsoft.com/library/windows/apps/hh465728) attributes, and dynamically maintain the **aria-valuenow** value to ensure that the current value is exposed. You should also set the [**aria-valuetext**](https://msdn.microsoft.com/library/windows/apps/hh968009) attribute to add more meaning to the exposed **aria-valuenow** value.

## Example


```HTML
<div role="slider" id="sl" aria-valuemin="1" aria-valuemax="5" aria-valuenow="3" aria-valuetext="good"…>
</div>

<script>
  // This function should be triggered when the slider value changes.
  function manageValue()
  {
    ...
    sl.setAttribute("aria-valuenow", currentValue);
    sl.setAttribute("aria-valuetext", currentValueText);
    ...
  }
</script>
```



## Related topics

<dl> <dt>

[ARIA Range Control Attributes Incompatible](aria-range-control-attribute-out-of-range.md)
</dt> </dl>

 

 



