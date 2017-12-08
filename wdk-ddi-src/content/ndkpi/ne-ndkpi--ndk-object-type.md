---
UID: NE.ndkpi._NDK_OBJECT_TYPE
title: NDK_OBJECT_TYPE
author: windows-driver-content
description: The NDK_OBJECT_TYPE enumeration defines types of Network Direct Kernel (NDK) objects.
old-location: netvista\ndk_object_type.htm
old-project: netvista
ms.assetid: 8CB39DF6-00DA-4480-A44E-62CAF1DB35CE
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDK_OBJECT_TYPE
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

# NDK_OBJECT_TYPE enumeration



## -description
<p>The <b>NDK_OBJECT_TYPE</b> enumeration defines  types of Network Direct Kernel (NDK) objects.</p>


## -syntax

````
typedef enum _NDK_OBJECT_TYPE { 
  NdkObjectTypeUndefined       = 0,
  NdkObjectTypeAdapter         = 1,
  NdkObjectTypeQp              = 2,
  NdkObjectTypeCq              = 3,
  NdkObjectTypeMr              = 4,
  NdkObjectTypeMw              = 5,
  NdkObjectTypePd              = 6,
  NdkObjectTypeSharedEndpoint  = 7,
  NdkObjectTypeConnector       = 8,
  NdkObjectTypeListener        = 9,
  NdkObjectTypeSrq             = 10,
  NdkObjectTypeMax             = 11
} NDK_OBJECT_TYPE;
````


## -enum-fields
<dl>

### -field NdkObjectTypeUndefined

<dd>
<p>Specifies  an undefined NDK  object.</p>
</dd>

### -field NdkObjectTypeAdapter

<dd>
<p>Specifies an NDK adapter object (<a href="..\ndkpi\ns-ndkpi--ndk-adapter.md">NDK_ADAPTER</a>).</p>
</dd>

### -field NdkObjectTypeQp

<dd>
<p>Specifies an NDK queue pair (QP) object (<a href="..\ndkpi\ns-ndkpi--ndk-qp.md">NDK_QP</a>).</p>
</dd>

### -field NdkObjectTypeCq

<dd>
<p>Specifies an NDK completion queue (CQ) object (<a href="..\ndkpi\ns-ndkpi--ndk-cq.md">NDK_CQ</a>).</p>
</dd>

### -field NdkObjectTypeMr

<dd>
<p>Specifies an NDK memory region (MR) object (<a href="..\ndkpi\ns-ndkpi--ndk-mr.md">NDK_MR</a>).</p>
</dd>

### -field NdkObjectTypeMw

<dd>
<p>Specifies an NDK memory window (MW) object (<a href="..\ndkpi\ns-ndkpi--ndk-mw.md">NDK_MW</a>).</p>
</dd>

### -field NdkObjectTypePd

<dd>
<p>Specifies an NDK protection domain (PD) object (<a href="..\ndkpi\ns-ndkpi--ndk-pd.md">NDK_PD</a>).</p>
</dd>

### -field NdkObjectTypeSharedEndpoint

<dd>
<p>Specifies an NDK shared endpoint object (<a href="..\ndkpi\ns-ndkpi--ndk-shared-endpoint.md">NDK_SHARED_ENDPOINT</a>).</p>
</dd>

### -field NdkObjectTypeConnector

<dd>
<p>Specifies an NDK connector object (<a href="..\ndkpi\ns-ndkpi--ndk-connector.md">NDK_CONNECTOR</a>).</p>
</dd>

### -field NdkObjectTypeListener

<dd>
<p>Specifies an NDK listener object (<a href="..\ndkpi\ns-ndkpi--ndk-listener.md">NDK_LISTENER</a>).</p>
</dd>

### -field NdkObjectTypeSrq

<dd>
<p>Specifies an NDK shared receive queue (SRQ) object (<a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a>).</p>
</dd>

### -field NdkObjectTypeMax

<dd>
<p>The maximum value for this enumeration. This value might change in future versions of the header files and binaries. 

</p>
</dd>
</dl>

## -remarks
<p>NDK objects include an <a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a> structure that packages the object type,  version, and other information.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-adapter.md">NDK_ADAPTER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-connector.md">NDK_CONNECTOR</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-cq.md">NDK_CQ</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-listener.md">NDK_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-mr.md">NDK_MR</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-mw.md">NDK_MW</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-object-header.md">NDK_OBJECT_HEADER</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-pd.md">NDK_PD</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-qp.md">NDK_QP</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-shared-endpoint.md">NDK_SHARED_ENDPOINT</a>
</dt>
<dt>
<a href="..\ndkpi\ns-ndkpi--ndk-srq.md">NDK_SRQ</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_OBJECT_TYPE enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>