---
UID: NF.ntifs.RtlInitializeSidEx
title: RtlInitializeSidEx function
author: windows-driver-content
description: The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure.
old-location: ifsk\rtlinitializesidex.htm
old-project: ifsk
ms.assetid: 367D8BC1-07F4-474E-913A-5F825320A70C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlInitializeSidEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows 10 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInitializeSidEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# RtlInitializeSidEx function



## -description
The <b>RtlInitializeSidEx</b> routine initializes a pre-allocated security identifier (SID) structure. 


## -syntax

````
NTSTATUS RtlInitializeSidEx(
  _Out_ PSID                      Sid,
  _In_  PSID_IDENTIFIER_AUTHORITY IdentifierAuthority,
  _In_  UCHAR                     SubAuthorityCount,
                                  ...
);
````


## -parameters

### -param Sid [out]

Pointer to a caller-allocated SID structure to be initialized. 

### -param IdentifierAuthority [in]

Pointer to an <a href="ifsk.sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a> structure to set in the SID structure. 

### -param SubAuthorityCount [in]

Number of sub-authorities to set in the SID.

### -param ... 

The values to set each sub-authority. The caller must specify the SubAuthorityCount argument.

## -returns
<b>RtlInitializeSid</b> returns one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The SID was successfully initialized.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The specified <i>SubAuthorityCount</i> value is invalid.

 

## -remarks
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
This routine is available on Windows 10 and later. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlsubauthoritysid">RtlSubAuthoritySid</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="ifsk.sid_identifier_authority">SID_IDENTIFIER_AUTHORITY</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeSidEx routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>