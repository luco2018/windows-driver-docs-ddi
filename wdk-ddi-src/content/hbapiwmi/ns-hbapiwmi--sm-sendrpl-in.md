---
UID: NS.hbapiwmi._SM_SendRPL_IN
title: SM_SendRPL_IN
author: windows-driver-content
description: The SM_SendRPL_IN structure is used to provide input parameters to the SM_SendRPL method.
old-location: storage\sm_sendrpl_in.htm
old-project: storage
ms.assetid: 5d97b852-57ba-4696-879b-d93a8f539304
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: SM_SendRPL_IN, SM_SendRPL_IN, *PSM_SendRPL_IN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_SendRPL_IN
req.alt-loc: hbapiwmi.h
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

# SM_SendRPL_IN structure



## -description
<p>The SM_SendRPL_IN structure is used to provide input parameters to the SM_SendRPL method.</p>


## -syntax

````
typedef struct _SM_SendRPL_IN {
  UCHAR HbaPortWWN[8];
  UCHAR AgentWWN[8];
  ULONG AgentDomain;
  ULONG PortIndex;
  ULONG InRespBufferMaxSize;
} SM_SendRPL_IN, *PSM_SendRPL_IN;
````


## -struct-fields
<dl>

### -field HbaPortWWN

<dd>
<p>A worldwide name (WWN) for the local port through which the read port list (RPL) command is sent.</p>
</dd>

### -field AgentWWN

<dd>
<p>A worldwide name (WWN) for the port that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification<i>.</i></p>
</dd>

### -field AgentDomain

<dd>
<p>The domain number for the domain controller that is to be queried for a list of ports of type FC_Port. For a definition of FC_Port, see the T11 committee's <i>Fibre Channel HBA API</i> specification.</p>
</dd>

### -field PortIndex

<dd>
<p>The port index of the first port in the list of ports of type FC_Port to be returned.</p>
</dd>

### -field InRespBufferMaxSize

<dd>
<p>The response buffer size.</p>
</dd>
</dl>

## -remarks
<p>The WMI tool suite generates a declaration of the SM_SendRPL_IN structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hbapiwmi.h (include Hbapiwmi.h)</dt>
</dl>
</td>
</tr>
</table>