---
UID: NS.rilapitypes.RILIMSSTATUS_V2~r1
title: RILIMSSTATUS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimsstatus_v2_2.htm
old-project: netvista
ms.assetid: 44aa62ac-510b-4f6d-9f17-f4abeadb06c1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILIMSSTATUS_V2,
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
req.alt-api: RILIMSSTATUS_V2
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

# RILIMSSTATUS_V2 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILIMSSTATUS_V2 {
  DWORD                     cbSize;
  DWORD                     dwParams;
  DWORD                     dwExecutor;
  HUICCAPP                  hUiccApp;
  DWORD                     dwAvailableServices;
  RILSMSFORMAT              dwSMSSupportedFormat;
  WCHAR [MAXLENGTH_ADDRESS] wszServingDomain;
} RILIMSSTATUS_V2, RILIMSSTATUS_V2;
````


## -struct-fields
<dl>

### -field cbSize

<dd></dd>

### -field dwParams

<dd></dd>

### -field dwExecutor

<dd></dd>

### -field hUiccApp

<dd></dd>

### -field dwAvailableServices

<dd></dd>

### -field dwSMSSupportedFormat

<dd></dd>

### -field wszServingDomain

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