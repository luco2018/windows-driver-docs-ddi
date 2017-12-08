---
UID: NF.vmbuskernelmodeclientlibapi.VmbPacketGetChannel
title: VmbPacketGetChannel function
author: windows-driver-content
description: The VmbPacketGetChannel function returns the VMBus channel with which a VMBus packet is associated.
old-location: netvista\vmbpacketgetchannel.htm
old-project: netvista
ms.assetid: BE5BB8CD-6B2F-4CFE-8A1E-B13BD9D7DBE7
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VmbPacketGetChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.alt-api: VmbPacketGetChannel
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# VmbPacketGetChannel function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]
The <b>VmbPacketGetChannel</b> function returns the VMBus channel with which a VMBus packet is associated.


## -syntax

````
VMBCHANNEL VmbPacketGetChannel(
  _In_ VMBPACKET PacketObject
);
````


## -parameters

### -param PacketObject [in]

The packet object.

## -returns
<b>VmbPacketGetChannel</b> returns a handle of the associated channel.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8.1
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012 R2
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.13
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>VmbusKernelModeClientLibApi.h (include VmbusKernelModeClientLibApi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Vmbkmcl.lib</dt>
</dl>
</td>
</tr>
</table>