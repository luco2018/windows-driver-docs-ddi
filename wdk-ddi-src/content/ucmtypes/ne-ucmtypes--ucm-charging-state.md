---
UID: NE.ucmtypes._UCM_CHARGING_STATE
title: UCM_CHARGING_STATE
author: windows-driver-content
description: Defines the charging state of a Type-C connector.
old-location: buses\ucm_charging_state.htm
old-project: usbref
ms.assetid: DDC3532A-0084-4C56-B540-C638AB7F7080
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
req.alt-api: UCM_CHARGING_STATE
req.alt-loc: Ucmtypes.h
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

# UCM_CHARGING_STATE enumeration



## -description
<p>Defines the charging state of a Type-C connector.</p>


## -syntax

````
typedef enum _UCM_CHARGING_STATE { 
  UcmChargingStateInvalid                   = 0x0,
  UcmChargingStateNotCharging,
  UcmChargingStateNominalCharging,
  UcmChargingStateSlowCharging,
      
    UcmChargingStateTrickleCharging
} UCM_CHARGING_STATE;
````


## -enum-fields
<dl>

### -field UcmChargingStateInvalid

<dd>
<p>Indicates the charging state is invalid.</p>
</dd>

### -field UcmChargingStateNotCharging

<dd>
<p>Indicates the port is not drawing a charge.</p>
</dd>

### -field UcmChargingStateNominalCharging

<dd>
<p>Indicates the port is drawing a nominal charge.</p>
</dd>

### -field UcmChargingStateSlowCharging

<dd>
<p>Indicates the port is drawing a slow charge.</p>
</dd>

### -field     
    UcmChargingStateTrickleCharging</b>

<dd>
<p>Indicates the port is drawing a trickle charge.</p>
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
<dt>Ucmtypes.h (include Ucmcx.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ucmmanager\ns-ucmmanager--ucm-connector-typec-attach-params.md">UCM_CONNECTOR_TYPEC_ATTACH_PARAMS</a>
</dt>
<dt>
<a href="..\ucmmanager\nf-ucmmanager-ucmconnectortypecattach.md">UcmConnectorTypeCAttach</a>
</dt>
<dt>
<a href="..\ucmmanager\ns-ucmmanager--ucm-connector-pd-conn-state-changed-params.md">UCM_CONNECTOR_PD_CONN_STATE_CHANGED_PARAMS</a>
</dt>
<dt>
<a href="..\ucmmanager\nf-ucmmanager-ucmconnectorpdconnectionstatechanged.md">UcmConnectorPdConnectionStateChanged</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_CHARGING_STATE enumeration%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>