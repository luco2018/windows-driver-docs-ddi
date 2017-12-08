---
UID: NF.ndis.NdisCmDeregisterSapComplete
title: NdisCmDeregisterSapComplete function
author: windows-driver-content
description: NdisCmDeregisterSapComplete returns the final status of a client's request, for which the call manager previously returned NDIS_STATUS_PENDING, to deregister a SAP.
old-location: netvista\ndiscmderegistersapcomplete.htm
old-project: netvista
ms.assetid: 92955e1e-6c5b-4e8e-a365-65ff4d0889a5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: NdisCmDeregisterSapComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisCmDeregisterSapComplete   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisCmDeregisterSapComplete   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisCmDeregisterSapComplete
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_CallManager_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
---

# NdisCmDeregisterSapComplete function



## -description
<b>NdisCmDeregisterSapComplete</b> returns the final status of a client's request, for which the call
  manager previously returned NDIS_STATUS_PENDING, to deregister a SAP.


## -syntax

````
VOID NdisCmDeregisterSapComplete(
  _In_ NDIS_STATUS Status,
  _In_ NDIS_HANDLE NdisSapHandle
);
````


## -parameters

### -param Status [in]

Specifies NDIS_STATUS_SUCCESS.

### -param NdisSapHandle [in]

Specifies the handle identifying the SAP.

## -returns
None

## -remarks
<b>NdisCmDeregisterSapComplete</b> notifies both NDIS and the client that the call manager has completed
    the SAP-deregistration request for which its 
    <a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">
    ProtocolCmDeregisterSap</a> function previously returned NDIS_STATUS_PENDING.

A call to 
    <b>NdisCmDeregisterSapComplete</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
    ProtocolClDeregisterSapComplete</a> function.

The call manager should consider the 
    <i>NdisSapHandle</i> invalid when 
    <b>NdisCmDeregisterSapComplete</b> returns control.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDeregisterSapComplete</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDeregisterSapComplete</b> instead.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/2fd1da54-c3fb-481e-99d2-1289a7159f14">NdisCmDeregisterSapComplete
   (NDIS 5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisCmDeregisterSapComplete
   (NDIS 5.1)</b>) in Windows XP.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.ndis_irql_callmanager_function">Irql_CallManager_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndisclderegistersap">NdisClDeregisterSap</a>
</dt>
<dt>
<a href="netvista.ndismcmderegistersapcomplete">NdisMCmDeregisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cl_deregister_sap_complete.md">
   ProtocolClDeregisterSapComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol_cm_deregister_sap.md">ProtocolCmDeregisterSap</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisCmDeregisterSapComplete function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>