---
title: Other Useful Features
description: Other Useful Features
ms.assetid: d7324263-8e66-4008-84dd-c95c7f69ad65
keywords:
- runtag
- before
- after
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Other Useful Features

You can use the `-runtag` option to insert a short text string into the names of the generated trace files. This can be useful when taking before-and-after runs around configuration changes, for example:


```
xbootmgr -trace boot -runtag before
```



Next, the system configuration is modified, and the trace repeated:


```
xbootmgr -trace boot -runtag after
```



The two traces are clearly identified, as shown in the following screen shot:

![screen shot of the command prompt window listing two trace (.etl) files](images/xbootmgrqs04.png)

 

 



