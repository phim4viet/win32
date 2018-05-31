---
Description: How to create mailslots. Mailslots are supported by three specialized functions CreateMailslot, GetMailslotInfo, and SetMailslotInfo. These functions are used by the mailslot server.
ms.assetid: 7f5a3b36-9583-43fc-a977-321c00a48edb
title: Creating a Mailslot
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Creating a Mailslot

Mailslots are supported by three specialized functions: [**CreateMailslot**](/windows/win32/Winbase/nf-winbase-createmailslota?branch=master), [**GetMailslotInfo**](/windows/win32/Winbase/nf-winbase-getmailslotinfo?branch=master), and [**SetMailslotInfo**](/windows/win32/Winbase/nf-winbase-setmailslotinfo?branch=master). These functions are used by the mailslot server.

The following code sample uses the [**CreateMailslot**](/windows/win32/Winbase/nf-winbase-createmailslota?branch=master) function to retrieve the handle to a mailslot named "sample\_mailslot". The code sample in [Writing to a Mailslot](writing-to-a-mailslot.md) shows how client application can write to this mailslot.


```C++
#include <windows.h>
#include <stdio.h>

HANDLE hSlot;
LPTSTR Slot = TEXT("\\\\.\\mailslot\\sample_mailslot");

BOOL WINAPI MakeSlot(LPTSTR lpszSlotName) 
{ 
    hSlot = CreateMailslot(lpszSlotName, 
        0,                             // no maximum message size 
        MAILSLOT_WAIT_FOREVER,         // no time-out for operations 
        (LPSECURITY_ATTRIBUTES) NULL); // default security
 
    if (hSlot == INVALID_HANDLE_VALUE) 
    { 
        printf("CreateMailslot failed with %d\n", GetLastError());
        return FALSE; 
    } 
    else printf("Mailslot created successfully.\n"); 
    return TRUE; 
}

void main()
{ 
   MakeSlot(Slot);
}
```



To create a mailslot that can be inherited by child processes, an application should change the [**SECURITY\_ATTRIBUTES**](https://msdn.microsoft.com/library/windows/desktop/aa379560) structure passed as the last parameter of [**CreateMailslot**](/windows/win32/Winbase/nf-winbase-createmailslota?branch=master). To do this, the application sets the **bInheritHandle** member of this structure to **TRUE** (the default setting is **FALSE**).

 

 


