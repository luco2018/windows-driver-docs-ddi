---
UID: NS.d3dkmthk._D3DKMT_UNLOCK2
title: D3DKMT_UNLOCK2
author: windows-driver-content
description: D3DKMT_UNLOCK2 describes an allocation to unlock.
old-location: display\d3dkmt_unlock2.htm
old-project: display
ms.assetid: 8651297B-BCF7-42A2-9175-D9D072E052D6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_UNLOCK2, D3DKMT_UNLOCK2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_UNLOCK2
req.alt-loc: d3dkmthk.h
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

# D3DKMT_UNLOCK2 structure



## -description
<p><b>D3DKMT_UNLOCK2</b> describes an allocation to unlock.</p>


## -syntax

````
typedef struct _D3DKMT_UNLOCK2 {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hAllocation;
} D3DKMT_UNLOCK2;
````


## -struct-fields
<dl>

### -field hDevice

<dd>
<p>The handle to the device.</p>
</dd>

### -field hAllocation

<dd>
<p>The handle to the allocation to unlock.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>