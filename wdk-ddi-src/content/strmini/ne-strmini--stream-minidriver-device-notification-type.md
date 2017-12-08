---
UID: NE.strmini._STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
title: STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
author: windows-driver-content
description: .
old-location: stream\stream_minidriver_device_notification_type.htm
old-project: stream
ms.assetid: 34DAA236-ACD0-4C25-BB45-00A81D2F131D
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PST_PARAMETER_DATA, ST_PARAMETER_DATA, *PST_PARAMETER_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE
req.alt-loc: Strmini.h
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

# STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE enumeration



## -description
<p></p>


## -syntax

````
typedef enum _STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE { 
  ReadyForNextDeviceRequest,
  DeviceRequestComplete,
  SignalMultipleDeviceEvents,
  SignalDeviceEvent,
  DeleteDeviceEvent,
#if (NTDDI_VERSION >= NTDDI_WINXP)
  SignalMultipleDeviceInstanceEvents,
#endif 
  DeviceNotificationMaximum
} STREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE, *PSTREAM_MINIDRIVER_DEVICE_NOTIFICATION_TYPE;
````


## -enum-fields
<dl>

### -field ReadyForNextDeviceRequest

<dd>
<p>Indicates that the minidriver is ready for the next device request.</p>
</dd>

### -field DeviceRequestComplete

<dd>
<p>Indicates that the specified device SRB has completed.</p>
</dd>

### -field SignalMultipleDeviceEvents

<dd></dd>

### -field SignalDeviceEvent

<dd></dd>

### -field DeleteDeviceEvent

<dd></dd>

### -field SignalMultipleDeviceInstanceEvents

<dd></dd>

### -field DeviceNotificationMaximum

<dd></dd>
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
<dt>Strmini.h</dt>
</dl>
</td>
</tr>
</table>