---
UID: NS.d3dkmthk._D3DKMT_DESTROY_OUTPUTDUPL
title: D3DKMT_DESTROY_OUTPUTDUPL
author: windows-driver-content
description: Reserved for system use. Do not use in your driver.
old-location: display\d3dkmt_destroy_outputdupl.htm
old-project: display
ms.assetid: ced3face-7f07-459f-8644-0062cd5db805
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_DESTROY_OUTPUTDUPL, D3DKMT_DESTROY_OUTPUTDUPL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_DESTROY_OUTPUTDUPL
req.alt-loc: D3dkmthk.h
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

# D3DKMT_DESTROY_OUTPUTDUPL structure



## -description
<p>Reserved for system use. Do not use in your driver.</p>


## -syntax

````
typedef struct _D3DKMT_DESTROY_OUTPUTDUPL {
  D3DKMT_HANDLE                  hAdapter;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  BOOL                           bDestroyAllContexts;
} D3DKMT_DESTROY_OUTPUTDUPL;
````


## -struct-fields
<dl>

### -field hAdapter

<dd></dd>

### -field VidPnSourceId

<dd></dd>

### -field bDestroyAllContexts

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
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