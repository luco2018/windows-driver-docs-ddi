---
UID: NE.d3dkmddi._DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
title: DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
author: windows-driver-content
description: Identifies the overlay plane's stereo flip mode. Only the DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE value is supported.
old-location: display\dxgk_multiplane_overlay_stereo_flip_mode.htm
old-project: display
ms.assetid: f226f276-c5d3-460d-9f52-c66ccfd3393f
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE
req.alt-loc: D3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE enumeration



## -description
<p>Identifies the overlay plane's stereo flip mode. Only the <b>DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE</b> value is supported.
</p>


## -syntax

````
typedef enum _DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE { 
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE    = 0,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0  = 1,
  DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1  = 2
} DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_MODE;
````


## -enum-fields
<dl>

### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_NONE

<dd>
<p>The overplay plane data is not presented in stereo mode.</p>
</dd>

### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME0

<dd>
<p>Reserved for system use. Do not use in your driver.</p>
</dd>

### -field DXGK_MULTIPLANE_OVERLAY_STEREO_FLIP_FRAME1

<dd>
<p>Reserved for system use. Do not use in your driver.</p>
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
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>