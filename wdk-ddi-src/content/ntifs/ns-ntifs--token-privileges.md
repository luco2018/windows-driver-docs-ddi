---
UID: NS.ntifs._TOKEN_PRIVILEGES
title: TOKEN_PRIVILEGES
author: windows-driver-content
description: TOKEN_PRIVILEGES contains information about a set of privileges for an access token.
old-location: ifsk\token_privileges.htm
old-project: ifsk
ms.assetid: f2f4b2b7-bec0-42c3-904b-cbc74ca76bb3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: TOKEN_PRIVILEGES, TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_PRIVILEGES
req.alt-loc: ntifs.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
---

# TOKEN_PRIVILEGES structure



## -description
<p>TOKEN_PRIVILEGES contains information about a set of privileges for an access token. </p>


## -syntax

````
typedef struct _TOKEN_PRIVILEGES {
  ULONG               PrivilegeCount;
  LUID_AND_ATTRIBUTES Privileges[ANYSIZE_ARRAY];
} TOKEN_PRIVILEGES, *PTOKEN_PRIVILEGES;
````


## -struct-fields
<dl>

### -field PrivilegeCount

<dd>
<p>Specifies the number of entries in the <b>Privileges</b> array. </p>
</dd>

### -field Privileges

<dd>
<p>Specifies an array of LUID_AND_ATTRIBUTES structures. Each structure contains the LUID and attributes of a privilege. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.luid">LUID</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--luid-and-attributes.md">LUID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="..\ntifs\ne-ntifs--token-information-class.md">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_PRIVILEGES structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>