---
UID: NS.hbapiwmi._SendRLS_IN
title: SendRLS_IN
author: windows-driver-content
description: The SendRLS_IN structure is used to deliver input parameter data to the SendRLS WMI method.
old-location: storage\sendrls_in.htm
old-project: storage
ms.assetid: ba78482f-243a-4f60-907e-8d5c4a702ef2
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SendRLS_IN, SendRLS_IN, *PSendRLS_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SendRLS_IN
req.alt-loc: hbapiwmi.h
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

# SendRLS_IN structure



## -description
<p>The SendRLS_IN structure is used to deliver input parameter data to the <a href="storage.sendrls">SendRLS</a> WMI method.</p>


## -syntax

````
typedef struct _SendRLS_IN {
  UCHAR PortWWN[8];
  UCHAR DestWWN[8];
} SendRLS_IN, *PSendRLS_IN;
````


## -struct-fields
<dl>

### -field PortWWN

<dd>
<p>Contains a worldwide name for the local port through which the read link error status block (RLS) command is sent. </p>
</dd>

### -field DestWWN

<dd>
<p>Contains a worldwide name for the destination port. </p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SendRLS_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="storage.msfc_hbaadaptermethods_wmi_class">MSFC_HBAAdapterMethods WMI Class</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.sendrls">SendRLS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SendRLS_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>