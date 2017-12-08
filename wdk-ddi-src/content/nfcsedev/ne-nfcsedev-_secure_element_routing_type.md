---
UID: NE.nfcsedev._SECURE_ELEMENT_ROUTING_TYPE
title: _SECURE_ELEMENT_ROUTING_TYPE
author: windows-driver-content
description: SECURE_ELEMENT_ROUTING_TYPE is a member of SECURE_ELEMENT_ROUTING_TABLE_ENTRY.
old-location: nfpdrivers\_secure_element_routing_type.htm
old-project: nfpdrivers
ms.assetid: 1420D957-546E-4795-A545-B098C411CCA5
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_ROUTING_TYPE, *PSECURE_ELEMENT_ROUTING_TYPE, SECURE_ELEMENT_ROUTING_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_ROUTING_TYPE
req.alt-loc: nfcsedev.h
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
---

# _SECURE_ELEMENT_ROUTING_TYPE enumeration



## -description
SECURE_ELEMENT_ROUTING_TYPE
is a member of <a href="nfpdrivers._secure_element_routing_table_entry">SECURE_ELEMENT_ROUTING_TABLE_ENTRY</a>.


## -syntax

````
typedef enum _SECURE_ELEMENT_ROUTING_TYPE { 
  RoutingTypeTech      = 0,
  RoutingTypeProtocol  = 1,
  RoutingTypeAid       = 2
} SECURE_ELEMENT_ROUTING_TYPE;
````


## -enum-fields

### -field RoutingTypeTech

NFC Forum technology-based routing type.


### -field RoutingTypeProtocol

NFC Forum protocol-based routing type.


### -field RoutingTypeAid

NFC Forum AID-based routing type.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Nfcsedev.h</dt>
</dl>
</td>
</tr>
</table>