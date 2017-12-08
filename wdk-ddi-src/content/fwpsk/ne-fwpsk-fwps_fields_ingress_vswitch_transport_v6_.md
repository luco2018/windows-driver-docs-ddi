---
UID: NE.fwpsk.FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6_
title: FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6_
author: windows-driver-content
description: The FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6 enumeration type specifies the data field identifiers for the FWPS_LAYER_INGRESS_VSWITCH_TRANSPORT_V6 run-time filtering layer.
old-location: netvista\fwps_fields_ingress_vswitch_transport_v6.htm
old-project: netvista
ms.assetid: 3b304001-3574-4e9d-abbb-0520e0a2cb34
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6_, FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6_ enumeration



## -description
The FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INGRESS_VSWITCH_TRANSPORT_V6 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layer</a>.


## -syntax

````
typedef enum FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V4_ { 
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_SOURCE_ADDRESS,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_DESTINATION_ADDRESS,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_PROTOCOL,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_SOURCE_PORT,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_DESTINATION_PORT,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VLAN_ID,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_TENANT_NETWORK_ID,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_ID,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_NETWORK_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_INTERFACE_ID,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_INTERFACE_TYPE,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_VM_ID,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_FLAGS,
  FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_MAX
} FWPS_FIELDS_INGRESS_VSWITCH_TRANSPORT_V6;
````


## -enum-fields

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_SOURCE_ADDRESS

The virtual switch ingress IP source address field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_DESTINATION_ADDRESS

The virtual switch ingress IP destination address field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_PROTOCOL

The virtual switch ingress IP protocol  field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_SOURCE_PORT

The virtual switch ingress IP source port field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_IP_DESTINATION_PORT

The virtual switch ingress IP destination port  field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VLAN_ID

The virtual switch ingress virtual LAN (VLAN) identifier field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_TENANT_NETWORK_ID

The virtual switch ingress virtual switch tenant network identifier field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_ID

The virtual switch ingress virtual switch identifier field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_NETWORK_TYPE

The virtual switch ingress virtual switch network type field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_INTERFACE_ID

The virtual switch ingress virtual switch source interface identifier field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_INTERFACE_TYPE

The virtual switch ingress virtual switch source interface type  field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_VSWITCH_SOURCE_VM_ID

The virtual switch ingress virtual switch source virtual machine (VM) identifier field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_FLAGS

The virtual switch ingress flags field.

### -field FWPS_FIELD_INGRESS_VSWITCH_TRANSPORT_V6_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 8.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Fwpsk.h (include Fwpsk.h)</dt>
</dl>
</td>
</tr>
</table>