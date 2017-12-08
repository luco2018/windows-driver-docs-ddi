---
UID: NF.ndis.NdisMCmCloseCallComplete
title: NdisMCmCloseCallComplete
author: windows-driver-content
description: NdisMCmCloseCallComplete returns the final status of a client's request, for which the MCM driver previously returned NDIS_STATUS_PENDING, to tear down a call.
old-location: netvista\ndismcmclosecallcomplete.htm
old-project: netvista
ms.assetid: 24477865-fb89-4078-99cb-1bf24249c7e2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisMCmCloseCallComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmCloseCallComplete (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisMCmCloseCallComplete
req.alt-loc: ndis.h
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# NdisMCmCloseCallComplete function



## -description
<p><b>NdisMCmCloseCallComplete</b> returns the final status of a client's request, for which the MCM driver
  previously returned NDIS_STATUS_PENDING, to tear down a call.</p>


## -syntax

````
VOID NdisMCmCloseCallComplete(
  _In_     NDIS_STATUS Status,
  _In_     NDIS_HANDLE NdisVcHandle,
  _In_opt_ NDIS_HANDLE NdisPartyHandle
);
````


## -parameters
<dl>

### -param Status [in]

<dd>
<p>Specifies the final status of the client's request that the MCM driver close the connection,
     either NDIS_STATUS_SUCCESS or any caller-determined NDIS_STATUS_<i>XXX</i> except NDIS_STATUS_PENDING.</p>
</dd>

### -param NdisVcHandle [in]

<dd>
<p>Specifies the handle to the VC for the call. This handle was supplied by NDIS when the VC was
     originally created, whether by the MCM driver with 
     <a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a> or as an input parameter
     to its 
     <a href="..\ndis\nc-ndis-protocol-co-create-vc.md">ProtocolCoCreateVc</a> function.</p>
</dd>

### -param NdisPartyHandle [in, optional]

<dd>
<p>Specifies either <b>NULL</b> if the 
     <i>NdisVcHandle</i> represents a point-to-point VC or the handle to the last remaining party on a
     multipoint connection, which the MCM driver obtained from its per-party state designated by the 
     <i>CallMgrPartyContext</i> passed as an input parameter to its 
     <a href="..\ndis\nc-ndis-protocol-cm-close-call.md">
     ProtocolCmCloseCall</a> function.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If an MCM driver's 
    <i>ProtocolCmCloseCall</i> function returns NDIS_STATUS_PENDING, it must call 
    <b>NdisMCmCloseCallComplete</b> subsequently to notify the client and NDIS that its attempt to break the
    connection has completed, whether successfully or with an error. A call to 
    <b>NdisMCmCloseCallComplete</b> causes NDIS to call the client's 
    <i>ProtocolClCloseCallComplete</i> function.</p>

<p>If it passes NDIS_STATUS_SUCCESS as the 
    <i>Status</i>, the MCM driver should consider the 
    <i>NdisVcHandle</i> (and 
    <i>NdisPartyHandle</i>, if any) unusable for transfers over the network as soon as it calls 
    <b>NdisMCmCloseCallComplete</b>. If the MCM driver originally created the VC, it should call 
    <a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a> with the same 
    <i>NdisVcHandle</i> that it just passed to 
    <b>NdisMCmCloseCallComplete</b>. If the client created this VC, the MCM driver can expect a call to its 
    <a href="..\ndis\nc-ndis-protocol-co-delete-vc.md">ProtocolCoDeleteVc</a> function with the
    
    <i>ProtocolVcContext</i>, designating its per-VC state in which it has stored the same 
    <i>NdisVcHandle</i>, as an input parameter.</p>

<p>Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmCloseCallComplete</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmCloseCallComplete</b> instead.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NDIS 6.0 and NDIS 5.1 drivers (see 
   <a href="https://msdn.microsoft.com/07ad3bfd-a5c6-458a-84d7-dbd21e0216e8">NdisMCmCloseCallComplete (NDIS
   5.1)</a>) in Windows Vista. Supported for NDIS 5.1 drivers (see 
   <b>NdisMCmCloseCallComplete (NDIS
   5.1)</b>) in Windows XP.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_mcm_function">Irql_MCM_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndiscmclosecallcomplete.md">NdisCmCloseCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdeactivatevc.md">NdisMCmDeactivateVc</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismcmdeletevc.md">NdisMCmDeleteVc</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-cl-close-call-complete.md">ProtocolClCloseCallComplete</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-co-delete-vc.md">ProtocolCoDeleteVc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMCmCloseCallComplete function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>