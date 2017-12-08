---
UID: NS.rilapitypes.RILTONESIGNALINFO_V1~r1
title: RILTONESIGNALINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v1_2.htm
old-project: netvista
ms.assetid: c6685a19-73d3-4725-90b8-7c859791381a
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILTONESIGNALINFO_V1,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILTONESIGNALINFO_V1
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILTONESIGNALINFO_V1 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILTONESIGNALINFO_V1 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1;
````


## -struct-fields
<dl>

### -field cbSize

<dd></dd>

### -field dwParams

<dd></dd>

### -field dwGPPTone

<dd></dd>

### -field dwGPP2Tone

<dd></dd>

### -field dwGPP2IsdnAlerting

<dd></dd>
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
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>