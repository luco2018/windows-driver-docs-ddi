---
UID: NF.ndis.NdisGetPhysicalAddressHigh
title: NdisGetPhysicalAddressHigh
author: windows-driver-content
description: NdisGetPhysicalAddressHigh returns the high-order part of a given physical address.
old-location: netvista\ndisgetphysicaladdresshigh.htm
old-project: netvista
ms.assetid: 17f8c6dd-7235-4ad0-bc3a-e801b53956ce
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisGetPhysicalAddressHigh
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisGetPhysicalAddressHigh   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisGetPhysicalAddressHigh   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisGetPhysicalAddressHigh
req.alt-loc: ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level
req.iface: 
---

# NdisGetPhysicalAddressHigh function



## -description
<p><b>NdisGetPhysicalAddressHigh</b> returns the high-order part of a given physical address.</p>


## -syntax

````
ULONG NdisGetPhysicalAddressHigh(
  _In_ NDIS_PHYSICAL_ADDRESS PhysicalAddress
);
````


## -parameters
<dl>

### -param PhysicalAddress [in]

<dd>
<p>Specifies a physical address of an OS-dependent size.</p>
</dd>
</dl>

## -returns
<p><b>NdisGetPhysicalAddressHigh</b> returns the value of the high-order part of the physical
     address.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/49d5c11b-ad21-4da7-a6c8-c72bc965d5a4">NdisGetPhysicalAddressHigh
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisGetPhysicalAddressHigh
   (NDIS 5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Any level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisgetphysicaladdresslow.md">NdisGetPhysicalAddressLow</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557129">NDIS_PHYSICAL_ADDRESS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndissetphysicaladdresshigh.md">NdisSetPhysicalAddressHigh</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetPhysicalAddressHigh function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>