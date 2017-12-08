---
UID: NE.ntifs.NETWORK_OPEN_INTEGRITY_QUALIFIER
title: NETWORK_OPEN_INTEGRITY_QUALIFIER
author: windows-driver-content
description: The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.
old-location: ifsk\network_open_integrity_qualifier.htm
old-project: ifsk
ms.assetid: 6a51ee2e-2df6-44f4-8e95-776851d743a6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: VOLUME_READ_PLEX_INPUT, VOLUME_READ_PLEX_INPUT, *PVOLUME_READ_PLEX_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NETWORK_OPEN_INTEGRITY_QUALIFIER
req.alt-loc: ntifs.h
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

# NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration



## -description
<p>The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.</p>


## -syntax

````
typedef enum  { 
  NetworkOpenIntegrityAny        = 0,
  NetworkOpenIntegrityNone       = 1,
  NetworkOpenIntegritySigned     = 2,
  NetworkOpenIntegrityEncrypted  = 3,
  NetworkOpenIntegrityMaximum    = 4
} NETWORK_OPEN_INTEGRITY_QUALIFIER;
````


## -enum-fields
<dl>

### -field NetworkOpenIntegrityAny

<dd>
<p>Indicates that the file has no integrity restrictions. That is, the file has no restrictions about how to sign, encrypt, and so on. </p>
</dd>

### -field NetworkOpenIntegrityNone

<dd>
<p>Indicates that the file is not signed or encrypted. </p>
</dd>

### -field NetworkOpenIntegritySigned

<dd>
<p>Indicates that the file is signed end-to-end. </p>
</dd>

### -field NetworkOpenIntegrityEncrypted

<dd>
<p>Indicates that the file is encrypted end-to-end. </p>
</dd>

### -field NetworkOpenIntegrityMaximum

<dd>
<p>Indicates that the file has the best integrity that is available. </p>
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
<p>This enumeration type is available starting with Windows Vista. </p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>