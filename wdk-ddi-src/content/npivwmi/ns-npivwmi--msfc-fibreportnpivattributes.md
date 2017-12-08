---
UID: NS.npivwmi._MSFC_FibrePortNPIVAttributes
title: MSFC_FibrePortNPIVAttributes
author: windows-driver-content
description: The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.
old-location: storage\msfc_fibreportnpivattributes.htm
old-project: storage
ms.assetid: 1641C3A0-E6D9-4E30-9E3C-3C09A14F591F
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MSFC_FibrePortNPIVAttributes, MSFC_FibrePortNPIVAttributes, *PMSFC_FibrePortNPIVAttributes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: npivwmi.h
req.include-header: Npivwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MSFC_FibrePortNPIVAttributes
req.alt-loc: npivwmi.h
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

# MSFC_FibrePortNPIVAttributes structure



## -description
<p>The MSFC_FibrePortNPIVAttributes structure contains attribute information for the virtual ports on an adapter.</p>


## -syntax

````
typedef struct _MSFC_FibrePortNPIVAttributes {
  UCHAR                           WWPN[8];
  UCHAR                           WWNN[8];
  ULONG                           NumberVirtualPorts;
  MSFC_VirtualFibrePortAttributes VirtualPorts[1];
} MSFC_FibrePortNPIVAttributes, *PMSFC_FibrePortNPIVAttributes;
````


## -struct-fields
<dl>

### -field WWPN

<dd>
<p>The world wide port name of the physical port.</p>
</dd>

### -field WWNN

<dd>
<p>The world wide node name of the physical port.</p>
</dd>

### -field NumberVirtualPorts

<dd>
<p>The number of virtual ports on the adapter.</p>
</dd>

### -field VirtualPorts

<dd>
<p>An array of virtual ports. The array length is specified in the <b>NumberVirtualPorts</b> member.</p>
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
<dt>Npivwmi.h (include Npivwmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.msfc_fibreportnpivattributes_wmi_class">MSFC_FibrePortNPIVAttributes WMI Class</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSFC_FibrePortNPIVAttributes structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>