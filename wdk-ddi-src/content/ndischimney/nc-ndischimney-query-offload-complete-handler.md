---
UID: NC.ndischimney.QUERY_OFFLOAD_COMPLETE_HANDLER
title: QUERY_OFFLOAD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol driver's or intermediate driver's ProtocolQueryOffloadComplete function to complete a query offload operation that the driver previously initiated by calling the NdisQueryOffload function.
old-location: netvista\protocolqueryoffloadcomplete.htm
old-project: netvista
ms.assetid: f521af88-eb96-4077-8882-9b1d02c6c87c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: BINARY_DATA, BINARY_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProtocolQueryOffloadComplete
req.alt-loc: Ndischimney.h
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

# QUERY_OFFLOAD_COMPLETE_HANDLER callback



## -description
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]</p>
<p>NDIS calls a protocol driver's or intermediate driver's 
  <i>ProtocolQueryOffloadComplete</i> function to complete a query offload operation that the driver
  previously initiated by calling the 
  <a href="netvista.ndisqueryoffload">NdisQueryOffload</a> function.</p>


## -prototype

````
QUERY_OFFLOAD_COMPLETE_HANDLER ProtocolQueryOffloadComplete;

VOID ProtocolQueryOffloadComplete(
  _In_ NDIS_HANDLE                       ProtocolBindingContext,
  _In_ PNDIS_PROTOCOL_OFFLOAD_BLOCK_LIST OffloadBlockList
)
{ ... }
````


## -parameters
<dl>

### -param ProtocolBindingContext [in]

<dd>
<p>A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.</p>
</dd>

### -param OffloadBlockList [in]

<dd>
<p>A pointer to an 
     <a href="..\ndischimney\ns-ndischimney--ndis-protocol-offload-block-list.md">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state that was queried or that was
     attempted to be queried.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>In response to an underlying offload target's or intermediate driver's call to the 
    <a href="..\ndischimney\nf-ndischimney-ndismqueryoffloadstatecomplete.md">
    NdisMQueryOffloadStateComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolQueryOffloadComplete</i> function.</p>

<p>An intermediate driver must propagate the completion of the query offload operation to the driver
    above it by calling 
    <b>NdisMQueryOffloadStateComplete</b>. For more information, see 
    <a href="netvista.propagating_the_completion_of_a_state_manipulation_operation">
    Propagating the Completion of a State-Manipulation Operation</a>.</p>

<p>From the NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure that was passed to its 
    <i>ProtocolQueryOffloadComplete</i> function, the intermediate driver constructs an 
    <a href="..\ndischimney\ns-ndischimney--ndis-miniport-offload-block-list.md">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure. For more information, see 
    <a href="netvista.reusing_an_ndis_protocol_offload_block_list_structure">Reusing an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST Structure</a>. When calling the 
    <b>NdisMQueryOffloadStateComplete</b> function, the intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this newly constructed NDIS_MINIPORT_OFFLOAD_BLOCK_LIST
    structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndischimney.h (include Ndischimney.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndischimney\nc-ndischimney-w-query-offload-handler.md">MiniportQueryOffload</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney--ndis-miniport-offload-block-list.md">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="..\ndischimney\nf-ndischimney-ndismqueryoffloadstatecomplete.md">
   NdisMQueryOffloadStateComplete</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>
</dt>
<dt>
<a href="..\ndischimney\ns-ndischimney--ndis-protocol-offload-block-list.md">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>
</dt>
<dt>
<a href="netvista.ndisqueryoffload">NdisQueryOffload</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20QUERY_OFFLOAD_COMPLETE_HANDLER callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>