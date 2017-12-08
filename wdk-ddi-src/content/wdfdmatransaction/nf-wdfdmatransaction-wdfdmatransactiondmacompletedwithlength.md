---
UID: NF.wdfdmatransaction.WdfDmaTransactionDmaCompletedWithLength
title: WdfDmaTransactionDmaCompletedWithLength function
author: windows-driver-content
description: The WdfDmaTransactionDmaCompletedWithLength method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer.
old-location: wdf\wdfdmatransactiondmacompletedwithlength.htm
old-project: wdf
ms.assetid: 7f436ac1-1e36-449c-a23f-b5729e5a20c2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDmaTransactionDmaCompletedWithLength
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdmatransaction.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfDmaTransactionDmaCompletedWithLength
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDmaTransactionDmaCompletedWithLength function



## -description
<p class="CCE_Message">[Applies to KMDF only]
The <b>WdfDmaTransactionDmaCompletedWithLength</b> method notifies the framework that a device's DMA transfer operation is complete and supplies the length of the completed transfer. 


## -syntax

````
BOOLEAN WdfDmaTransactionDmaCompletedWithLength(
  _In_  WDFDMATRANSACTION DmaTransaction,
  _In_  size_t            TransferredLength,
  _Out_ NTSTATUS          *Status
);
````


## -parameters

### -param DmaTransaction [in]

A handle to a DMA transaction object that the driver obtained from a previous call to <a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>.

### -param TransferredLength [in]

The number of bytes that the device transferred in the current DMA transfer.

### -param Status [out]

A pointer to a location that receives the status of the DMA transfer. For more information, see the Remarks section for <a href="wdf.wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>.

## -returns
<b>WdfDmaTransactionDmaCompletedWithLength</b> returns <b>FALSE</b> and <i>Status</i> receives STATUS_MORE_PROCESSING_REQUIRED if additional transfers are needed to complete the DMA transaction. The method returns <b>TRUE</b> if no additional transfers are required. 

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
When your driver calls the <b>WdfDmaTransactionDmaCompletedWithLength</b> method, the framework ends the current transfer and, if necessary, starts a new one.

The <b>WdfDmaTransactionDmaCompletedWithLength</b> method behaves the same as <a href="wdf.wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>, except that drivers call <b>WdfDmaTransactionDmaCompletedWithLength</b> for devices that report the number of bytes that were transferred. The framework uses the reported byte count to determine the beginning of the next DMA transfer for the specified DMA transaction, if multiple transfers are needed to complete the transaction.

For more information about completing DMA transfers, see <a href="wdf.completing_a_dma_transfer">Completing a DMA Transfer</a>.

The following code example is from the <a href="wdf.sample_kmdf_drivers">PLX9x5x</a> sample driver. This example calls <a href="wdf.wdfdmatransactiongetcurrentdmatransferlength">WdfDmaTransactionGetCurrentDmaTransferLength</a> to determine the current transfer's original length, and then it calculates the actual transfer length. Next, the example calls <b>WdfDmaTransactionDmaCompletedWithLength</b> to report the actual transfer length to the framework. If the current transfer is the last one for the transaction, the example calls a private routine that completes the I/O request.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdmatransaction.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;=DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdmatransactioncreate">WdfDmaTransactionCreate</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiondmacompleted">WdfDmaTransactionDmaCompleted</a>
</dt>
<dt>
<a href="wdf.wdfdmatransactiongetcurrentdmatransferlength">WdfDmaTransactionGetCurrentDmaTransferLength</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDmaTransactionDmaCompletedWithLength method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>