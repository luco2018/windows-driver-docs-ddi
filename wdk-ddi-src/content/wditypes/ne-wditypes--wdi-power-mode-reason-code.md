---
UID: NE.wditypes._WDI_POWER_MODE_REASON_CODE
title: WDI_POWER_MODE_REASON_CODE
author: windows-driver-content
description: The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.
old-location: netvista\wdi_power_mode_reason_code.htm
old-project: netvista
ms.assetid: F9FAA622-A844-4D9F-A0E6-D919C1FAD3AB
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_WORKITEM_CONFIG, WDF_WORKITEM_CONFIG, *PWDF_WORKITEM_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_POWER_MODE_REASON_CODE
req.alt-loc: wditypes.hpp
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WDI_POWER_MODE_REASON_CODE enumeration



## -description
<p>The WDI_POWER_MODE_REASON_CODE enumeration defines the reasons for entering the Power Save state.</p>


## -syntax

````
typedef enum _WDI_POWER_MODE_REASON_CODE { 
  WDI_POWER_MODE_REASON_CODE_NO_CHANGE             = 0,
  WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP       = 1,
  WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE     = 2,
  WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP          = 3,
  WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE  = 4,
  WDI_POWER_MODE_REASON_CODE_OTHERS                = 5
} WDI_POWER_MODE_REASON_CODE;
````


## -enum-fields
<dl>

### -field WDI_POWER_MODE_REASON_CODE_NO_CHANGE

<dd>
<p>Device is initially in this state and has not changed since.</p>
</dd>

### -field WDI_POWER_MODE_REASON_CODE_NONCOMPLIANT_AP

<dd>
<p>AP is not compliant. As to be in CAM.</p>
</dd>

### -field WDI_POWER_MODE_REASON_CODE_LEGACY_P2P_DEVICE

<dd>
<p>WFD device is legacy.</p>
</dd>

### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_AP

<dd>
<p>AP is compliant.</p>
</dd>

### -field WDI_POWER_MODE_REASON_CODE_COMPLIANT_P2P_DEVICE

<dd>
<p>All connected WFD device can do PSM.</p>
</dd>

### -field WDI_POWER_MODE_REASON_CODE_OTHERS

<dd>
<p>Other reason.</p>
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
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>