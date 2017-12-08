---
UID: NF.wdfcompanion.WdfDeviceInitSetCompanionEventCallbacks
title: WdfDeviceInitSetCompanionEventCallbacks function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfdeviceinitsetcompanioneventcallbacks.htm
old-project: wdf
ms.assetid: 7320238d-0c7f-423c-8de7-2b22d02d77bd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDeviceInitSetCompanionEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
req.alt-api: WdfDeviceInitSetCompanionEventCallbacks
req.alt-loc: wdfcompanion.h
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
req.product: Windows 10 or later.
---

# WdfDeviceInitSetCompanionEventCallbacks function



## -description

			For internal use only.


## -syntax

````
VOID WdfDeviceInitSetCompanionEventCallbacks(
  _In_ PWDFDEVICE_INIT                DeviceInit,
  _In_ PWDF_COMPANION_EVENT_CALLBACKS CompanionEventCallbacks
);
````


## -parameters

### -param DeviceInit [in]


### -param CompanionEventCallbacks [in]


## -returns
This method does not return a value.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.23
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfcompanion.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>