---
UID: NS.NFCSEDEV._SECURE_ELEMENT_ENDPOINT_INFO
title: _SECURE_ELEMENT_ENDPOINT_INFO
author: windows-driver-content
description: SECURE_ELEMENT_ENDPOINT_INFO is a member of SECURE_ELEMENT_ENDPOINT_LIST.
old-location: nfpdrivers\_secure_element_endpoint_info.htm
old-project: nfpdrivers
ms.assetid: C1D812BD-55F0-44F7-BCC8-81CC758EDEF3
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _SECURE_ELEMENT_ENDPOINT_INFO, SECURE_ELEMENT_ENDPOINT_INFO, *PSECURE_ELEMENT_ENDPOINT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: nfcsedev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SECURE_ELEMENT_ENDPOINT_INFO
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

# _SECURE_ELEMENT_ENDPOINT_INFO structure



## -description
SECURE_ELEMENT_ENDPOINT_INFO is a member of <a href="nfpdrivers._secure_element_endpoint_list">SECURE_ELEMENT_ENDPOINT_LIST</a>.


## -syntax

````
typedef struct _SECURE_ELEMENT_ENDPOINT_INFO {
  GUID                guidSecureElementId;
  SECURE_ELEMENT_TYPE eSecureElementType;
} SECURE_ELEMENT_ENDPOINT_INFO, *P_SECURE_ELEMENT_ENDPOINT_INFO;
````


## -struct-fields

### -field guidSecureElementId

This is a unique identifier for the secure element.

### -field eSecureElementType

Type of secure element endpoint (NFCEE).

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