---
UID: NC.wdfdmaenabler.EVT_WDF_DMA_ENABLER_ENABLE
title: EVT_WDF_DMA_ENABLER_ENABLE
author: windows-driver-content
description: A driver's EvtDmaEnablerEnable event callback function enables a device's DMA capability after the device enters its working (D0) state.
old-location: wdf\evtdmaenablerenable.htm
old-project: wdf
ms.assetid: b6344a06-98ee-48c0-8fd5-76edfc71af2b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_REMOVE_LOCK_OPTIONS, WDF_REMOVE_LOCK_OPTIONS, *PWDF_REMOVE_LOCK_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdmaenabler.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtDmaEnablerEnable
req.alt-loc: WdfDmaEnabler.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_DMA_ENABLER_ENABLE callback



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>A driver's <i>EvtDmaEnablerEnable</i> event callback function enables a device's DMA capability after the device enters its working (D0) state. </p>


## -prototype

````
EVT_WDF_DMA_ENABLER_ENABLE EvtDmaEnablerEnable;

NTSTATUS EvtDmaEnablerEnable(
  _In_ WDFDMAENABLER DmaEnabler
)
{ ... }
````


## -parameters
<dl>

### -param DmaEnabler [in]

<dd>
<p>A handle to a DMA enabler object. </p>
</dd>
</dl>

## -returns
<p><i>EvtDmaEnablerEnable</i>  must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if it encounters no errors. Otherwise, this callback function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. </p>

## -remarks
<p>To register an <i>EvtDmaEnablerEnable</i> callback function, a function driver for a DMA device places the callback function's address in a <a href="..\wdfdmaenabler\ns-wdfdmaenabler--wdf-dma-enabler-config.md">WDF_DMA_ENABLER_CONFIG</a> structure before the driver calls <a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>.</p>

<p>For more information about the <i>EvtDmaEnablerEnable</i> callback function, see <a href="wdf.supporting_power_management_for_dma_devices">Supporting Power Management for DMA Devices</a>.</p>

<p>The <i>EvtDmaEnablerEnable</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="wdf.creating_pageable_code_in_a_kmdf_driver">pageable</a>.</p>

<p>To define an <i>EvtDmaEnablerEnable</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtDmaEnablerEnable</i> callback function that is named <i>MyDmaEnablerEnable</i>, use the <b>EVT_WDF_DMA_ENABLER_ENABLE</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_DMA_ENABLER_ENABLE</b> function type is defined in the WdfDmaEnabler.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DMA_ENABLER_ENABLE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>WdfDmaEnabler.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL (see Remarks section)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdmaenabler\nc-wdfdmaenabler-evt-wdf-dma-enabler-disable.md">EvtDmaEnablerDisable</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\ns-wdfdmaenabler--wdf-dma-enabler-config.md">WDF_DMA_ENABLER_CONFIG</a>
</dt>
<dt>
<a href="..\wdfdmaenabler\nf-wdfdmaenabler-wdfdmaenablercreate.md">WdfDmaEnablerCreate</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DMA_ENABLER_ENABLE callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>