---
UID: NE.d3d10umddi.D3D10_DDI_STENCIL_OP
title: D3D10_DDI_STENCIL_OP
author: windows-driver-content
description: The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's CreateDepthStencilState function.
old-location: display\d3d10_ddi_stencil_op.htm
old-project: display
ms.assetid: 624decb3-6279-45ba-8cdd-5a52de80dd71
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D10_DDI_STENCIL_OP
req.alt-loc: d3d10umddi.h
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

# D3D10_DDI_STENCIL_OP enumeration



## -description
<p>The D3D10_DDI_STENCIL_OP enumeration type contains values that identify operations on stencil buffers in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdepthstencilstate.md">CreateDepthStencilState</a> function.</p>


## -syntax

````
typedef enum D3D10_DDI_STENCIL_OP { 
  D3D10_DDI_STENCIL_OP_KEEP      = 1,
  D3D10_DDI_STENCIL_OP_ZERO      = 2,
  D3D10_DDI_STENCIL_OP_REPLACE   = 3,
  D3D10_DDI_STENCIL_OP_INCR_SAT  = 4,
  D3D10_DDI_STENCIL_OP_DECR_SAT  = 5,
  D3D10_DDI_STENCIL_OP_INVERT    = 6,
  D3D10_DDI_STENCIL_OP_INCR      = 7,
  D3D10_DDI_STENCIL_OP_DECR      = 8
} D3D10_DDI_STENCIL_OP;
````


## -enum-fields
<dl>

### -field D3D10_DDI_STENCIL_OP_KEEP

<dd>
<p>Do not update the entry in the stencil buffer. D3D10_DDI_STENCIL_OP_KEEP is the default value.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_ZERO

<dd>
<p>Set the stencil-buffer entry to 0.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_REPLACE

<dd>
<p>Replace the stencil-buffer entry with a reference value.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_INCR_SAT

<dd>
<p>Increment the stencil-buffer entry, clamping to the maximum value.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_DECR_SAT

<dd>
<p>Decrement the stencil-buffer entry, clamping to zero.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_INVERT

<dd>
<p>Invert the bits in the stencil-buffer entry.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_INCR

<dd>
<p>Increment the stencil-buffer entry, wrapping to zero if the new value exceeds the maximum value.</p>
</dd>

### -field D3D10_DDI_STENCIL_OP_DECR

<dd>
<p>Decrement the stencil-buffer entry, wrapping to the maximum value if the new value is less than zero.</p>
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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdepthstencilstate.md">CreateDepthStencilState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_STENCIL_OP enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>