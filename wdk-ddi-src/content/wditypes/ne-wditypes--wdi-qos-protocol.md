---
UID: NE.wditypes._WDI_QOS_PROTOCOL
title: WDI_QOS_PROTOCOL
author: windows-driver-content
description: The WDI_QOS_PROTOCOL enumeration defines Wi-Fi QOS protocols.
old-location: netvista\wdi_qos_protocol.htm
old-project: netvista
ms.assetid: 39466BF7-0517-4113-9C94-26D8691CCCC1
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
req.alt-api: WDI_QOS_PROTOCOL
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

# WDI_QOS_PROTOCOL enumeration



## -description
<p>The WDI_QOS_PROTOCOL enumeration defines Wi-Fi QOS protocols.</p>


## -syntax

````
typedef enum _WDI_QOS_PROTOCOL { 
  WDI_QOS_PROTOCOL_NONE  = 0x00,
  WDI_QOS_PROTOCOL_WMM   = 0x01,
  WDI_QOS_PROTOCOL_11E   = 0x02
} WDI_QOS_PROTOCOL;
````


## -enum-fields
<dl>

### -field WDI_QOS_PROTOCOL_NONE

<dd>
<p>None</p>
</dd>

### -field WDI_QOS_PROTOCOL_WMM

<dd>
<p>Wi-Fi Multimedia (WMM, formerly known as Wireless Multimedia Extensions)</p>
</dd>

### -field WDI_QOS_PROTOCOL_11E

<dd>
<p>802.11E</p>
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