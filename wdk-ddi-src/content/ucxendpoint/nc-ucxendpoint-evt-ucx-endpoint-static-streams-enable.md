---
UID: NC.ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE
author: windows-driver-content
description: The client driver's implementation that UCX calls to enable the static streams.
old-location: buses\evt_ucx_endpoint_static_streams_enable.htm
old-project: usbref
ms.assetid: eb40623f-b13f-4c3f-b3ac-687cba323ce2
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UCXUSBDEVICE_INFO,
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: PFN_UCM_CONNECTOR_GET_OPERATING_MODE
req.alt-loc: ucxendpoint.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE callback



## -description
<p>The client driver's implementation that UCX calls to enable the static streams.</p>


## -prototype

````
EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE EvtUcxEndpointStaticStreamsEnable;

VOID EvtUcxEndpointStaticStreamsEnable(
  _In_ UCXENDPOINT Endpoint,
  _In_ UCXSSTREAMS UcxStaticStreams,
  _In_ WDFREQUEST  Request
)
{ ... }

typedef EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE PFN_UCM_CONNECTOR_GET_OPERATING_MODE;
````


## -parameters
<dl>

### -param Endpoint [in]

<dd>
<p>A handle to a UCXENDPOINT object that represents the endpoint.</p>
</dd>

### -param UcxStaticStreams [in]

<dd>
<p>A handle to a UCX object that represents the static streams.</p>
</dd>

### -param Request [in]

<dd>
<p>Contains the URB for the <b>URB_FUNCTION_OPEN_STATIC_STREAMS</b>.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.</p>

<p>The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucxendpoint.h (include Ucxclass.h or Ucxendpoint.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL</p>
</td>
</tr>
</table>