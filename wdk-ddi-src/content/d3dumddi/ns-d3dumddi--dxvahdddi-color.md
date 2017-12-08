---
UID: NS.d3dumddi._DXVAHDDDI_COLOR
title: DXVAHDDDI_COLOR
author: windows-driver-content
description: The DXVAHDDDI_COLOR union contains information that specifies color with either a YCbCr or RGB color structure.
old-location: display\dxvahdddi_color.htm
old-project: display
ms.assetid: ac1a2fae-29f1-4143-9d43-b10db300de03
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXVAHDDDI_COLOR, DXVAHDDDI_COLOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVAHDDDI_COLOR
req.alt-loc: d3dumddi.h
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

# DXVAHDDDI_COLOR structure



## -description
<p>The DXVAHDDDI_COLOR union contains information that specifies color with either a YCbCr or RGB color structure.  </p>


## -syntax

````
typedef union _DXVAHDDDI_COLOR {
  DXVAHDDDI_COLOR_RGBA   RGB;
  DXVAHDDDI_COLOR_YCbCrA YCbCr;
} DXVAHDDDI_COLOR;
````


## -struct-fields
<dl>

### -field RGB

<dd>
<p>[in] A <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color-rgba.md">DXVAHDDDI_COLOR_RGBA</a> structure that describes color in RGB terms. </p>
</dd>

### -field YCbCr

<dd>
<p>[in] A <a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color-ycbcra.md">DXVAHDDDI_COLOR_YCbCrA</a> structure that describes color in a YCbCr terms. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>DXVAHDDDI_COLOR is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color-rgba.md">DXVAHDDDI_COLOR_RGBA</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi--dxvahdddi-color-ycbcra.md">DXVAHDDDI_COLOR_YCbCrA</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVAHDDDI_COLOR union%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>