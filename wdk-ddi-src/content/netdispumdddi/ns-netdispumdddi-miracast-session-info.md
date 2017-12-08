---
UID: NS.netdispumdddi.MIRACAST_SESSION_INFO
title: MIRACAST_SESSION_INFO
author: windows-driver-content
description: Contains info on a wireless display (Miracast) connected session.
old-location: display\miracast_session_info.htm
old-project: display
ms.assetid: 48F3CB86-5181-4E1E-9E7F-88FB2CD3640A
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: MIRACAST_SESSION_INFO, MIRACAST_SESSION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_SESSION_INFO
req.alt-loc: Netdispumdddi.h
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

# MIRACAST_SESSION_INFO structure



## -description
<p>Contains info on a wireless display (Miracast) connected session.</p>


## -syntax

````
typedef union {
  struct {
    UINT MonitorConnected  :1;
    UINT ReducedModeListDueToBandwidth  :1;
    UINT Reserved  :30;
  };
  UINT Value;
} MIRACAST_SESSION_INFO;
````


## -struct-fields
<dl>

### -field MonitorConnected

<dd>
<p>If set, the monitor (the source) is connected to a Miracast sink.</p>
</dd>

### -field ReducedModeListDueToBandwidth

<dd>
<p>If set, the user-mode driver has reduced the modes exposed to the operating system based on the current suggested encode rate.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use and should be set to zero.</p>
</dd>

### -field Value

<dd>
<p>Holds a 32-bit value that identifies the Miracast connected session.</p>
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
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>