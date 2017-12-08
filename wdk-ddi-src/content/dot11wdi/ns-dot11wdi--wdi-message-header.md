---
UID: NS.dot11wdi._WDI_MESSAGE_HEADER
title: WDI_MESSAGE_HEADER
author: windows-driver-content
description: The WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI command messages must start with this header.
old-location: netvista\wdi_message_header.htm
old-project: netvista
ms.assetid: 69c3ebf5-8805-47d0-a507-d2e3e1d1b0df
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDI_MESSAGE_HEADER, WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_MESSAGE_HEADER
req.alt-loc: dot11wdi.h
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

# WDI_MESSAGE_HEADER structure



## -description
<p>The 
  WDI_MESSAGE_HEADER structure defines the WDI message header. All WDI  command messages must start with this header.</p>


## -syntax

````
typedef struct _WDI_MESSAGE_HEADER {
  UINT16      PortId;
  UINT16      Reserved;
  NDIS_STATUS Status;
  UINT32      TransactionId;
  UINT32      IhvSpecificId;
} WDI_MESSAGE_HEADER, *PWDI_MESSAGE_HEADER;
````


## -struct-fields
<dl>

### -field PortId

<dd>
<p>Specifies the identifier for the Port object that this command is targeted for. For commands on the Adapter object, this is 0xFFFF.</p>
</dd>

### -field Reserved

<dd>
<p>This member is reserved.</p>
</dd>

### -field Status

<dd>
<p>Specifies the operation completion status for output messages. For input messages, this field is reserved.</p>
</dd>

### -field TransactionId

<dd>
<p>Specifies the transaction ID. This value is used to match host-sent messages with function responses.  This value must be unique among all outstanding transactions.  For notifications, the TransactionId must be set to 0 by the function.</p>
</dd>

### -field IhvSpecificId

<dd>
<p>Specifies an IHV-specific ID for this message. This can be used by IHVs for debugging purpose.</p>
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
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>