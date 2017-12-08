---
UID: NF.ucmmanager.UCM_CONNECTOR_PD_CONFIG_INIT
title: UCM_CONNECTOR_PD_CONFIG_INIT
author: windows-driver-content
description: Initializes a UCM_CONNECTOR_PD_CONFIG structure.
old-location: buses\ucm_connector_pd_config_init.htm
old-project: usbref
ms.assetid: 59663F6C-5C8E-4403-8097-7E6D9A075A60
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCM_CONNECTOR_PD_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_CONNECTOR_PD_CONFIG_INIT
req.alt-loc: Ucmmanager.h
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
req.product: Windows 10 or later.
---

# UCM_CONNECTOR_PD_CONFIG_INIT function



## -description
<p>Initializes a <a href="..\ucmmanager\ns-ucmmanager--ucm-connector-pd-config.md">UCM_CONNECTOR_PD_CONFIG</a> structure.</p>


## -syntax

````
FORCEINLINE void UCM_CONNECTOR_PD_CONFIG_INIT(
  _Out_ PUCM_CONNECTOR_PD_CONFIG Config,
  _In_  ULONG                    SupportedPowerRoles
);
````


## -parameters
<dl>

### -param Config [out]

<dd>
<p>Pointer to a caller-allocated <a href="..\ucmmanager\ns-ucmmanager--ucm-connector-pd-config.md">UCM_CONNECTOR_PD_CONFIG</a> structure to initialize.</p>
</dd>

### -param SupportedPowerRoles [in]

<dd>
<p>A bitwise OR of <a href="..\ucmtypes\ne-ucmtypes--ucm-power-role.md">UCM_POWER_ROLE</a>-typed flags.</p>
</dd>
</dl>

## -returns
<p>This function does not return a value.</p>

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
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucmmanager.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorcreate.md">UcmConnectorCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CONNECTOR_PD_CONFIG_INIT function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>