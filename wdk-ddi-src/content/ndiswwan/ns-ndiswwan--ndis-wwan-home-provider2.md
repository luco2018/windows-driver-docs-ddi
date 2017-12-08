---
UID: NS.ndiswwan._NDIS_WWAN_HOME_PROVIDER2
title: NDIS_WWAN_HOME_PROVIDER2
author: windows-driver-content
description: The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.
old-location: netvista\ndis_wwan_home_provider2.htm
old-project: netvista
ms.assetid: B01039CF-F4AC-4374-BBB8-ACB204BC40E2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_HOME_PROVIDER2, NDIS_WWAN_HOME_PROVIDER2, *PNDIS_WWAN_HOME_PROVIDER2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_HOME_PROVIDER2
req.alt-loc: ndiswwan.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NDIS_WWAN_HOME_PROVIDER2 structure



## -description
<p>The NDIS_WWAN_HOME_PROVIDER2 structure describes details of a home network provider.</p>


## -syntax

````
typedef struct _NDIS_WWAN_HOME_PROVIDER2 {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
  WWAN_PROVIDER2     Provider;
} NDIS_WWAN_HOME_PROVIDER2, *PNDIS_WWAN_HOME_PROVIDER2;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The header with type, revision, and size information about the NDIS_WWAN_HOME_PROVIDER2 structure. The MB
     Service sets the header with the values that are shown in the following table when it sends the data
     structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     </p>
<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
<p>Type</p>
</td>
<td>
<p>NDIS_OBJECT_TYPE_DEFAULT</p>
</td>
</tr>
<tr>
<td>
<p>Revision</p>
</td>
<td>
<p>NDIS_WWAN_HOME_PROVIDER_REVISION_2</p>
</td>
</tr>
<tr>
<td>
<p>Size</p>
</td>
<td>
<p>sizeof(NDIS_WWAN_HOME_PROVIDER2)</p>
</td>
</tr>
</table>
<p> </p>
<p>For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>.</p>
</dd>

### -field uStatus

<dd>
<p>The status of the home provider operation.</p>
</dd>

### -field Provider

<dd>
<p>A formatted <a href="..\wwan\ns-wwan--wwan-provider2.md">WWAN_PROVIDER2</a> object that describes the details of a home network provider.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported in Windows 8 and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wwan\ns-wwan--wwan-provider2.md">WWAN_PROVIDER2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_HOME_PROVIDER2 structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>