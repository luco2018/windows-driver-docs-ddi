---
UID: NS.iddcx.IDARG_IN_OPM_GET_INFOMATION
title: IDARG_IN_OPM_GET_INFOMATION
author: windows-driver-content
description: Gives information about the OPM.
old-location: display\idarg_in_opm_get_infomation.htm
old-project: display
ms.assetid: 14d0585d-6fa1-4934-a4f2-fe5e20d4a324
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: IDARG_IN_OPM_GET_INFOMATION,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDARG_IN_OPM_GET_INFOMATION
req.alt-loc: iddcx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _Must_inspect_result_
req.iface: 
---

# IDARG_IN_OPM_GET_INFOMATION structure



## -description
<p>
                 Gives information about the OPM.</p>


## -syntax

````
typedef struct IDARG_IN_OPM_GET_INFOMATION {
  IDDCX_OPM_GET_INFO_PARAMETERS GetInfoParameters;
} IDARG_IN_OPM_GET_INFOMATION, *IDARG_IN_OPM_GET_INFOMATION;
````


## -struct-fields
<dl>

### -field GetInfoParameters

<dd>
<p>
                     [in] Parameters for the get information request
                 </p>
</dd>
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
<dt>Iddcx.h</dt>
</dl>
</td>
</tr>
</table>