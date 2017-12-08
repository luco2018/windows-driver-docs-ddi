---
UID: NS.d3dumddi._D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
title: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
author: windows-driver-content
description: The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the pfnSetDisplayPrivateDriverFormatCb function.
old-location: display\d3dddicb_setdisplayprivatedriverformat.htm
old-project: display
ms.assetid: b10b020d-f18c-403d-b1ee-79552d18ad4e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT, D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT
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

# D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure



## -description
<p>The D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure describes the private-format attribute to set for a video present source in a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a> function.</p>


## -syntax

````
typedef struct _D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  UINT                           PrivateDriverFormatAttribute;
} D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT;
````


## -struct-fields
<dl>

### -field VidPnSourceId

<dd>
<p>[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to set a private-format attribute on (that is, the identifier of the primary surface to set a private-format attribute on). </p>
</dd>

### -field PrivateDriverFormatAttribute

<dd>
<p>[in] A UINT value that specifies the private-format attribute to set for the video present source that the <b>VidPnSourceId</b> member specifies.</p>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-setdisplayprivatedriverformatcb.md">pfnSetDisplayPrivateDriverFormatCb</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_SETDISPLAYPRIVATEDRIVERFORMAT structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>