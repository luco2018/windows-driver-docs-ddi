---
UID: NE.d3d10umddi.D3D10_DDI_PRIMITIVE_TOPOLOGY
title: D3D10_DDI_PRIMITIVE_TOPOLOGY
author: windows-driver-content
description: The D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration type contains values that identify primitive topologies in a call to the driver's IaSetTopology function.
old-location: display\d3d10_ddi_primitive_topology.htm
old-project: display
ms.assetid: 49e7f8d3-36e2-41d6-9cea-ea0c284586e6
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
req.alt-api: D3D10_DDI_PRIMITIVE_TOPOLOGY
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

# D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration



## -description
<p>The D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration type contains values that identify primitive topologies in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-ia-settopology.md">IaSetTopology</a> function.</p>


## -syntax

````
typedef enum D3D10_DDI_PRIMITIVE_TOPOLOGY { 
  D3D10_DDI_PRIMITIVE_TOPOLOGY_UNDEFINED                   = 0,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_POINTLIST                   = 1,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST                    = 2,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP                   = 3,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST                = 4,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP               = 5,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST_ADJ                = 10,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP_ADJ               = 11,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST_ADJ            = 12,
  D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP_ADJ           = 13,
#if D3D11DDI_MINOR_HEADER_VERSION >= 1
  D3D11_DDI_PRIMITIVE_TOPOLOGY_1_CONTROL_POINT_PATCHLIST   = 33,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_2_CONTROL_POINT_PATCHLIST   = 34,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_3_CONTROL_POINT_PATCHLIST   = 35,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_4_CONTROL_POINT_PATCHLIST   = 36,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_5_CONTROL_POINT_PATCHLIST   = 37,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_6_CONTROL_POINT_PATCHLIST   = 38,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_7_CONTROL_POINT_PATCHLIST   = 39,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_8_CONTROL_POINT_PATCHLIST   = 40,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_9_CONTROL_POINT_PATCHLIST   = 41,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_10_CONTROL_POINT_PATCHLIST  = 42,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_11_CONTROL_POINT_PATCHLIST  = 43,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_12_CONTROL_POINT_PATCHLIST  = 44,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_13_CONTROL_POINT_PATCHLIST  = 45,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_14_CONTROL_POINT_PATCHLIST  = 46,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_15_CONTROL_POINT_PATCHLIST  = 47,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_16_CONTROL_POINT_PATCHLIST  = 48,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_17_CONTROL_POINT_PATCHLIST  = 49,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_18_CONTROL_POINT_PATCHLIST  = 50,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_19_CONTROL_POINT_PATCHLIST  = 51,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_20_CONTROL_POINT_PATCHLIST  = 52,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_21_CONTROL_POINT_PATCHLIST  = 53,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_22_CONTROL_POINT_PATCHLIST  = 54,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_23_CONTROL_POINT_PATCHLIST  = 55,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_24_CONTROL_POINT_PATCHLIST  = 56,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_25_CONTROL_POINT_PATCHLIST  = 57,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_26_CONTROL_POINT_PATCHLIST  = 58,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_27_CONTROL_POINT_PATCHLIST  = 59,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_28_CONTROL_POINT_PATCHLIST  = 60,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_29_CONTROL_POINT_PATCHLIST  = 61,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_30_CONTROL_POINT_PATCHLIST  = 62,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_31_CONTROL_POINT_PATCHLIST  = 63,
  D3D11_DDI_PRIMITIVE_TOPOLOGY_32_CONTROL_POINT_PATCHLIST  = 64

#endif } D3D10_DDI_PRIMITIVE_TOPOLOGY;
````


## -enum-fields
<dl>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_UNDEFINED

<dd>
<p>The primitive topology is undefined.</p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_POINTLIST

<dd>
<p>Vertices are rendered as a collection of isolated points.</p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST

<dd>
<p>Vertices are rendered as a list of isolated straight line segments.</p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP

<dd>
<p>Vertices are rendered as a single polyline.</p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST

<dd>
<p>
      Vertices are rendered as a sequence of isolated triangles. Each group of three vertices defines a separate triangle.
     </p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP

<dd>
<p>Vertices are rendered as a triangle strip. </p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINELIST_ADJ

<dd>
<p>The primitives contain room for adjacency information.  </p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_LINESTRIP_ADJ

<dd>
<p>The primitives contain room for adjacency information. </p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLELIST_ADJ

<dd>
<p>The primitives contain room for adjacency information. </p>
</dd>

### -field D3D10_DDI_PRIMITIVE_TOPOLOGY_TRIANGLESTRIP_ADJ

<dd>
<p>The primitives contain room for adjacency information. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_1_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_2_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions.</p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_3_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions.</p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_4_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions.</p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_5_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions.</p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_6_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_7_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_8_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_9_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_10_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_11_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_12_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_13_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_14_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_15_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_16_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_17_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_18_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_19_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_20_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_21_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_22_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_23_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_24_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_25_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_26_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_27_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_28_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_29_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_30_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_31_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
</dd>

### -field D3D11_DDI_PRIMITIVE_TOPOLOGY_32_CONTROL_POINT_PATCHLIST

<dd>
<p>Supported in Windows 7 and later versions. </p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-ia-settopology.md">IaSetTopology</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_PRIMITIVE_TOPOLOGY enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>