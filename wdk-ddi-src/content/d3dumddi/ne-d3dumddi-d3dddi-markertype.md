---
UID: NE.d3dumddi.D3DDDI_MARKERTYPE
title: D3DDDI_MARKERTYPE
author: windows-driver-content
description: Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.
old-location: display\d3dddi_markertype.htm
old-project: display
ms.assetid: 55A48F87-B96C-42E7-B9B4-3C829097CAE9
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MARKERTYPE
req.alt-loc: D3dumddi.h
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

# D3DDDI_MARKERTYPE enumeration



## -description
<p>Indicates the type of Event Tracing for Windows (ETW) marker event that the user-mode display driver supports.</p>


## -syntax

````
typedef enum D3DDDI_MARKERTYPE { 
  D3DDDIMT_NONE,
  D3DDDIMT_PROFILE
} D3DDDI_MARKERTYPE;
````


## -enum-fields
<dl>

### -field D3DDDIMT_NONE

<dd>
<p>No marker type is supported. This type is set on creation of the display device.</p>
</dd>

### -field D3DDDIMT_PROFILE

<dd>
<p>Profile mode, where the driver estimates the length of time the GPU takes to execute certain operations. The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.</p>
<p>See Remarks of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setmarkermode.md">pfnSetMarkerMode</a> function for more info.</p>
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
<dt>D3dumddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setmarkermode.md">pfnSetMarkerMode</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MARKERTYPE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>