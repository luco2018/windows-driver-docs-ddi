---
UID: NS.rilapitypes.RILCALLINFO_V1~r1
title: RILCALLINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfo_v1_2.htm
old-project: netvista
ms.assetid: f630afff-d3ca-4ada-aa8c-5062893f2de5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILCALLINFO_V1,
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
req.alt-api: RILCALLINFO_V1
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

# RILCALLINFO_V1 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef struct _RILCALLINFO_V1 {
  DWORD                           cbSize;
  DWORD                           dwParams;
  DWORD                           dwExecutor;
  DWORD                           dwID;
  RILCALLINFODIRECTION            dwDirection;
  RILCALLINFOSTATUS               dwStatus;
  RILCALLTYPE                     dwType;
  RILCALLINFOMULTIPARTY           dwMultiparty;
  RILADDRESS                      raAddress;
  RILSUBADDRESS                   rsaSubAddress;
  WCHAR [MAXLENGTH_DESCRIPTION]   wszDescription;
  RILREMOTEPARTYINFOVALUE         dwNumberPresentationIndicator;
  RILREMOTEPARTYINFOVALUE         dwNamePresentationIndicator;
  BOOL                            fAlienCall;
  RILCALLINFODISCONNECTINITIATOR  dwDisconnectInitiator;
  RILCALLINFODISCONNECTREASON     dwDisconnectReason;
  RILCALLDISCONNECTDETAILS        stDisconnectDetails;
} RILCALLINFO_V1, RILCALLINFO_V1;
````


## -struct-fields
<dl>

### -field cbSize

<dd></dd>

### -field dwParams

<dd></dd>

### -field dwExecutor

<dd></dd>

### -field dwID

<dd></dd>

### -field dwDirection

<dd></dd>

### -field dwStatus

<dd></dd>

### -field dwType

<dd></dd>

### -field dwMultiparty

<dd></dd>

### -field raAddress

<dd></dd>

### -field rsaSubAddress

<dd></dd>

### -field wszDescription

<dd></dd>

### -field dwNumberPresentationIndicator

<dd></dd>

### -field dwNamePresentationIndicator

<dd></dd>

### -field fAlienCall

<dd></dd>

### -field dwDisconnectInitiator

<dd></dd>

### -field dwDisconnectReason

<dd></dd>

### -field stDisconnectDetails

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