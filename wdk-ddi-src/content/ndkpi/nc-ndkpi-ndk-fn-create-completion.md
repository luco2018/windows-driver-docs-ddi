---
UID: NC.ndkpi.NDK_FN_CREATE_COMPLETION
title: NDK_FN_CREATE_COMPLETION
author: windows-driver-content
description: The NdkCreateCompletion (NDK_FN_CREATE_COMPLETION) function completes the creation of an NDK object.
old-location: netvista\ndk_fn_create_completion.htm
old-project: netvista
ms.assetid: C7A2792C-FDAE-4525-A8B1-7F8F6BA8249A
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
req.alt-api: NdkCreateCompletion
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

# NDK_FN_CREATE_COMPLETION callback



## -description
<p>The <i>NdkCreateCompletion</i> (<i>NDK_FN_CREATE_COMPLETION</i>) function completes the creation of an NDK object.</p>


## -prototype

````
NDK_FN_CREATE_COMPLETION NdkCreateCompletion;

VOID NdkCreateCompletion(
  _In_opt_ PVOID             Context,
  _In_     NTSTATUS          Status,
  _In_     NDK_OBJECT_HEADER *pNdkObject
)
{ ... }
````


## -parameters
<dl>

### -param Context [in, optional]

<dd>
<p>The context value passed to the NDK provider when a consumer calls an object creation function. The creation function  provides the context with the asynchronous create completion request <i>NdkCreateCompletion</i> (<i>NDK_FN_CREATE_COMPLETION</i>) function pointer.</p>
</dd>

### -param Status [in]

<dd>
<p>The asynchronous completion status for the create request. See the object creation functions (for example, <a href="..\ndkpi\nc-ndkpi-ndk-fn-create-cq.md">NDK_FN_CREATE_CQ</a>) for completion status codes that can be returned for each type of object.</p>
</dd>

### -param pNdkObject [in]

<dd>
<p>A pointer to an NDK object header (<a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a>).</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>NDK objects are created with asynchronous functions. These asynchronous object creation functions take an <i>NDK_FN_CREATE_COMPLETION</i> function pointer as an input parameter. </p>

<p>An NDK provider can return STATUS_PENDING from an asynchronous object creation function. In this case, the  NDK provider must call the create completion function to indicate that the object creation is complete. </p>

<p>Any status other status code indicates inline completion. In this case, the provider must not call the create request completion function. If the create request function returns an NT_STATUS status code other than STATUS_PENDING, the created object must be returned in an output parameter with the create request function. </p>

<p>For create requests that return STATUS_PENDING and later complete with STATUS_SUCCESS asynchronously, the created object must be returned by the create completion function with the <i>pNdkObject</i> parameter and the provider must not access the object output parameter of the create request function.</p>

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
<a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-connector.md">NDK_FN_CREATE_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-cq.md">NDK_FN_CREATE_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-listener.md">NDK_FN_CREATE_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-mr.md">NDK_FN_CREATE_MR</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-mw.md">NDK_FN_CREATE_MW</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-pd.md">NDK_FN_CREATE_PD</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-qp.md">NDK_FN_CREATE_QP</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-qp-with-srq.md">NDK_FN_CREATE_QP_WITH_SRQ</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-shared-endpoint.md">NDK_FN_CREATE_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk-fn-create-srq.md">NDK_FN_CREATE_SRQ</a>
</dt>
<dt>
<a href="netvista.ndkpi_object_lifetime_requirements">NDKPI Object Lifetime Requirements</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CREATE_COMPLETION callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>