---
UID: NS.d3d12umddi.D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
author: windows-driver-content
description: Video decode format count data.
old-location: display\d3d12ddi-video-decode-format-count-data-0032.htm
old-project: display
ms.assetid: 3d28fe10-1dfc-4017-9ab0-d8b8e2d45448
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032
req.alt-loc: d3d12umddi.h
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

# D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 structure



## -description
<p>Video decode format count data.</p>


## -syntax

````
typedef struct _D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032 {
  UINT                                      NodeIndex;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020  Configuration;
  UINT                                      FormatCount;
} D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032, D3D12DDI_VIDEO_DECODE_FORMAT_COUNT_DATA_0032;
````


## -struct-fields
<dl>

### -field NodeIndex

<dd>
<p>Node index.</p>
</dd>

### -field Configuration

<dd>
<p>Configuration.</p>
</dd>

### -field FormatCount

<dd>
<p>Format count.</p>
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
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>