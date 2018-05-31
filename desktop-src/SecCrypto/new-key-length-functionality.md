---
Description: The Base Provider used only 40-bit symmetric keys.
ms.assetid: 7cfa6c7e-e30c-4829-9989-9567b42ad92f
title: New Key-length Functionality
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# New Key-length Functionality

The Base Provider used only 40-bit [*symmetric keys*](security.s_gly#-security-symmetric-key-gly). The addition of longer keys in the Enhanced Provider, and the fact that imported keys can be of arbitrary length requires a method of querying the length for a specific key. To find the actual length of a key in bits, a user can call [**CryptGetKeyParam**](/windows/win32/Wincrypt/nf-wincrypt-cryptgetkeyparam?branch=master) with the KP\_KEYLEN parameter value. The length of the key is returned in the **DWORD** pointed to by the *pbData* parameter.

> [!Note]  
> To protect against stepping-down [*cryptanalysis*](security.c_gly#-security-cryptoanalysis-gly) attacks, applications must check for insufficient [*key lengths*](security.k_gly#-security-key-length-gly) and notify the user when one is encountered.

 

The following example shows how to query the length of a key.


```C++
#pragma comment(lib, "crypt32.lib")

#include <windows.h>
#include <Wincrypt.h>
#include <stdio.h>
void main()
{
    HCRYPTPROV hProv = NULL;
    HCRYPTKEY hKey = NULL;

    DWORD dwKeyLength;
    DWORD dwLen = sizeof(DWORD);
    // Copyright (C) Microsoft.  All rights reserved.
    // Acquire a cryptographic context.
    if (!CryptAcquireContext(&amp;hProv,
                              NULL,
                              NULL,
                              PROV_RSA_FULL,
                              CRYPT_VERIFYCONTEXT))
    {
        printf("CryptAcquireContext failed.\n");
        goto Cleanup;
    }

    // Generate a key.
    if (!CryptGenKey(
                hProv,    
                CALG_RC2,    
                0,    
                &amp;hKey))
    {
        printf("CryptGenKey failed.\n");
        goto Cleanup;
    }

    // Query the key length.
    if (!CryptGetKeyParam(
            hKey,    
            KP_KEYLEN,    
            (BYTE*)&amp;dwKeyLength,
            &amp;dwLen,    
            0))
    {
        printf("CryptGetKeyParam failed.\n");
        goto Cleanup;
    }
    else
    {
        printf("The key is %d bits long. \n", dwKeyLength);
    } 

Cleanup:

    if (hKey)
        CryptDestroyKey(hKey);

    if (hProv)
        CryptReleaseContext(hProv, 0);
}
```



 

 


