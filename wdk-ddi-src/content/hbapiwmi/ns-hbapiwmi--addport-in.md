---
UID: NS.hbapiwmi._AddPort_IN
title: AddPort_IN
author: windows-driver-content
description: The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the AddPort WMI method to the HBA miniport driver.
old-location: storage\addport_in.htm
old-project: storage
ms.assetid: c9cdc0fc-e292-4142-a070-50a25a2a5673
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: AddPort_IN, AddPort_IN, *PAddPort_IN
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
req.alt-api: AddPort_IN
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

# AddPort_IN structure



## -description
<p>The AddPort_IN structure is used by a WMI client to deliver the input parameter data of the <a href="storage.addport">AddPort</a> WMI method to the HBA miniport driver.</p>


## -syntax

````
typedef struct _AddPort_IN {
  UCHAR PortWWN[8];
} AddPort_IN, *PAddPort_IN;
````


## -struct-fields
<dl>

### -field PortWWN

<dd>
<p>Contains a worldwide name that indicates the port whose events are to be reported. </p>
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
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.addport">AddPort</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AddPort_IN structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>