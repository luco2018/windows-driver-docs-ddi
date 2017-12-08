---
UID: NS.1394._IRB_REQ_SEND_PHY_PACKET
title: _IRB_REQ_SEND_PHY_PACKET
author: windows-driver-content
description: This structure contains the fields necessary to carry out a SendPhyPacket request.
old-location: ieee\irb_req_send_phy_packet.htm
old-project: IEEE
ms.assetid: 32C96259-3A35-4BD3-96A4-A9F2A5FDAB99
ms.author: windowsdriverdev
ms.date: 11/29/2017
ms.keywords: _IRB_REQ_SEND_PHY_PACKET, IRB_REQ_SEND_PHY_PACKET
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRB_REQ_SEND_PHY_PACKET
req.alt-loc: 1394.h
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

# _IRB_REQ_SEND_PHY_PACKET structure



## -description
This structure contains the fields necessary to carry out a SendPhyPacket request.


## -syntax

````
typedef struct _IRB_REQ_SEND_PHY_PACKET {
  ULONG          Flags;
  ULONG          GenerationCount;
  ULARGE_INTEGER PhyPacket;
} IRB_REQ_SEND_PHY_PACKET;
````


## -struct-fields

### -field Flags

Specifies any nondefault settings for this operation. Set to ASYNC_FLAGS_NO_STATUS to always return success from the send PHY packet operation, regardless of whether the send PHY packet succeeds or fails.

### -field GenerationCount

Specifies the bus reset generation as known by the device driver that submits this request. If the specified generation count does not match the actual generation of the bus, this request is returned with a status of STATUS_INVALID_GENERATION.

### -field PhyPacket

Specifies the 64-bit PHY packet that is sent to the 1394 bus.

## -remarks
If successful, the new 1394 bus driver (1394ohci.sys) sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS. If <b>u.SendPhyPacket.GenerationCount</b> does not match the current bus generation count, the new 1394 bus driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_INVALID_GENERATION

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>1394.h</dt>
</dl>
</td>
</tr>
</table>