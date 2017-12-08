---
UID: NS.d3dkmthk._D3DKMT_SETVIDPNSOURCEOWNER2
title: D3DKMT_SETVIDPNSOURCEOWNER2
author: windows-driver-content
description: Used to set the VidPN source owner.
old-location: display\d3dkmt-setvidpnsourceowner2.htm
old-project: display
ms.assetid: 6a6477db-23ad-42ad-b1cb-d81c7be4cf38
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DKMT_SETVIDPNSOURCEOWNER2, D3DKMT_SETVIDPNSOURCEOWNER2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_SETVIDPNSOURCEOWNER2
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

# D3DKMT_SETVIDPNSOURCEOWNER2 structure



## -description
<p>Used to set the VidPN source owner.</p>


## -syntax

````
typedef struct _D3DKMT_SETVIDPNSOURCEOWNER2 {
  D3DKMT_SETVIDPNSOURCEOWNER1 Version1;
  HANDLE const*               *pVidPnSourceNtHandles;
} D3DKMT_SETVIDPNSOURCEOWNER2;
````


## -struct-fields
<dl>

### -field Version1

<dd>
<p>The previous method used to set the VidPN source owner.</p>
</dd>

### -field pVidPnSourceNtHandles

<dd>
<p>A handle to the VidPN source owner handles.</p>
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
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>