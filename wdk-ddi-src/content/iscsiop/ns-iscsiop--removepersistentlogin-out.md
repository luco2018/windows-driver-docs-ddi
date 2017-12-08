---
UID: NS.iscsiop._RemovePersistentLogin_OUT
title: RemovePersistentLogin_OUT
author: windows-driver-content
description: The RemovePersistentLogin_OUT structure holds the output data for the RemovePersistentLogin method.
old-location: storage\removepersistentlogin_out.htm
old-project: storage
ms.assetid: 2b5aee65-ccf6-42c6-9bb3-dff93cb53cf0
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: RemovePersistentLogin_OUT, RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiop.h
req.include-header: Iscsiop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RemovePersistentLogin_OUT
req.alt-loc: iscsiop.h
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

# RemovePersistentLogin_OUT structure



## -description
<p>The RemovePersistentLogin_OUT structure holds the output data for the <a href="storage.removepersistentlogin">RemovePersistentLogin</a> method.</p>


## -syntax

````
typedef struct _RemovePersistentLogin_OUT {
  ULONG Status;
} RemovePersistentLogin_OUT, *PRemovePersistentLogin_OUT;
````


## -struct-fields
<dl>

### -field Status

<dd>
<p>On output from <b>RemovePersistentLogin</b>, the status of the operation. For a list of status qualifiers, see <a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>.</p>
</dd>
</dl>

## -remarks
<p>You must implement this method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Iscsiop.h (include Iscsiop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.iscsi_status_qualifiers">ISCSI_STATUS_QUALIFIERS</a>
</dt>
<dt>
<a href="storage.removepersistentlogin">RemovePersistentLogin</a>
</dt>
<dt>
<a href="..\iscsiop\ns-iscsiop--removepersistentlogin-in.md">RemovePersistentLogin_IN</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20RemovePersistentLogin_OUT structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>