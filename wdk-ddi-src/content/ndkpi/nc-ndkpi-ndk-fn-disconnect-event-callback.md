---
UID: NC.ndkpi.NDK_FN_DISCONNECT_EVENT_CALLBACK
title: NDK_FN_DISCONNECT_EVENT_CALLBACK
author: windows-driver-content
description: The NdkDisconnectEventCallback (NDK_FN_DISCONNECT_EVENT_CALLBACK) function is called by the NDK provider once when the peer disconnects.
old-location: netvista\ndk_fn_disconnect_event_callback.htm
old-project: netvista
ms.assetid: AC6A7CD4-D553-4E6D-B6BF-C30CDA541EB5
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkDisconnectEventCallback
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
---

# NDK_FN_DISCONNECT_EVENT_CALLBACK callback



## -description
<p>The <i>NdkDisconnectEventCallback</i> (<i>NDK_FN_DISCONNECT_EVENT_CALLBACK</i>) function  is called by the NDK provider once when the peer disconnects. </p>


## -prototype

````
NDK_FN_DISCONNECT_EVENT_CALLBACK NdkDisconnectEventCallback;

VOID NdkDisconnectEventCallback(
  _In_opt_ PVOID DisconnectEventContext
)
{ ... }
````


## -parameters
<dl>

### -param DisconnectEventContext [in, optional]

<dd>
<p>A context area that was specified in the <i>DisconnectEvent</i> parameter of the <i>NdkCompleteConnect</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-complete-connect.md">NDK_FN_COMPLETE_CONNECT</a>)  or <i>NdkAccept</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-accept.md">NDK_FN_ACCEPT</a>)  function when the completion queue (CQ)  object was created.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><i>NdkDisconnectEventCallback</i> is a callback function for connection disconnect events.  A disconnect notification callback function is specified for a connection with the <i>NdkCompleteConnect</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-complete-connect.md">NDK_FN_COMPLETE_CONNECT</a>) function on the initiator side and with the <i>NdkAccept</i> (<a href="..\ndkpi\nc-ndkpi-ndk-fn-accept.md">NDK_FN_ACCEPT</a>) function on the listener side. The NDK provider invokes this callback only once when the peer disconnects. The provider should not flush outstanding work requests when it indicates a disconnect event because of an incoming disconnect request from the peer.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>None supported</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-accept.md">NDK_FN_ACCEPT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-complete-connect.md">NDK_FN_COMPLETE_CONNECT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_DISCONNECT_EVENT_CALLBACK callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>