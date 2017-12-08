---
UID: NE.d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
title: D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.
old-location: display\d3dkmdt_vidpn_present_path_importance.htm
old-project: display
ms.assetid: a48eda3c-84cb-4413-a325-79c330be3f18
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
req.alt-loc: d3dkmdt.h
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

# D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration



## -description
<p>The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.</p>


## -syntax

````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE { 
  D3DKMDT_VPPI_UNINITIALIZED  = 0,
  D3DKMDT_VPPI_PRIMARY        = 1,
  D3DKMDT_VPPI_SECONDARY      = 2,
  D3DKMDT_VPPI_TERTIARY       = 3,
  D3DKMDT_VPPI_QUATERNARY     = 4,
  D3DKMDT_VPPI_QUINARY        = 5,
  D3DKMDT_VPPI_SENARY         = 6,
  D3DKMDT_VPPI_SEPTENARY      = 7,
  D3DKMDT_VPPI_OCTONARY       = 8,
  D3DKMDT_VPPI_NONARY         = 9,
  D3DKMDT_VPPI_DENARY         = 10
} D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE;
````


## -enum-fields
<dl>

### -field D3DKMDT_VPPI_UNINITIALIZED

<dd>
<p>Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE has not yet been assigned a meaningful value.</p>
</dd>

### -field D3DKMDT_VPPI_PRIMARY

<dd>
<p>Indicates importance level 1.</p>
</dd>

### -field D3DKMDT_VPPI_SECONDARY

<dd>
<p>Indicates importance level 2.</p>
</dd>

### -field D3DKMDT_VPPI_TERTIARY

<dd>
<p>Indicates importance level 3.</p>
</dd>

### -field D3DKMDT_VPPI_QUATERNARY

<dd>
<p>Indicates importance level 4.</p>
</dd>

### -field D3DKMDT_VPPI_QUINARY

<dd>
<p>Indicates importance level 5.</p>
</dd>

### -field D3DKMDT_VPPI_SENARY

<dd>
<p>Indicates importance level 6.</p>
</dd>

### -field D3DKMDT_VPPI_SEPTENARY

<dd>
<p>Indicates importance level 7.</p>
</dd>

### -field D3DKMDT_VPPI_OCTONARY

<dd>
<p>Indicates importance level 8.</p>
</dd>

### -field D3DKMDT_VPPI_NONARY

<dd>
<p>Indicates importance level 9.</p>
</dd>

### -field D3DKMDT_VPPI_DENARY

<dd>
<p>Indicates importance level 10.</p>
</dd>
</dl>

## -remarks
<p>As the numeric value of a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value increases, the importance decreases. For example, level 3 is less important than level 2.</p>

<p>A variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE can have any integer value in the range 0 through 255, but only the values 0 through 10 have names.</p>

<p>It is useful to rank the video present paths in a video present network (VidPN) according to importance. For example, a path that represents the primary view can be assigned a higher importance than other paths so that it gets the best source and target mode sets.</p>

<p>The <b>ImportanceOrdinal</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value. Path importance ordinal numbers are unique within a given VidPN topology. </p>

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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt--d3dkmdt-vidpn-present-path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>