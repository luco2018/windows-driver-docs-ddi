---
UID: NF.wdm.RtlNumberOfClearBits
title: RtlNumberOfClearBits function
author: windows-driver-content
description: The RtlNumberOfClearBits routine returns a count of the clear bits in a given bitmap variable.
old-location: kernel\rtlnumberofclearbits.htm
old-project: kernel
ms.assetid: 739dc01d-7340-449f-8fe6-64e5c8284436
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlNumberOfClearBits
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlNumberOfClearBits
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL (See Remarks section)
req.product: Windows 10 or later.
---

# RtlNumberOfClearBits function



## -description
The <b>RtlNumberOfClearBits</b> routine returns a count of the clear bits in a given bitmap variable. 


## -syntax

````
ULONG RtlNumberOfClearBits(
  _In_ PRTL_BITMAP BitMapHeader
);
````


## -parameters

### -param BitMapHeader [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="kernel.rtlinitializebitmap">RtlInitializeBitMap</a> routine. 

## -returns
<b>RtlNumberOfClearBits</b> returns the number of bits that are currently clear. 

## -remarks
Callers of <b>RtlNumberOfClearBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfClearBits</b> can be called at any IRQL.

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
Version
</th>
<td width="70%">
Available starting with Windows 2000.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= APC_LEVEL (See Remarks section)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>
</dt>
<dt>
<a href="kernel.rtlfindclearbits">RtlFindClearBits</a>
</dt>
<dt>
<a href="kernel.rtlfindclearruns">RtlFindClearRuns</a>
</dt>
<dt>
<a href="kernel.rtlfindfirstrunclear">RtlFindFirstRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindlastbackwardrunclear">RtlFindLastBackwardRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindlongestrunclear">RtlFindLongestRunClear</a>
</dt>
<dt>
<a href="kernel.rtlfindnextforwardrunclear">RtlFindNextForwardRunClear</a>
</dt>
<dt>
<a href="kernel.rtlinitializebitmap">RtlInitializeBitMap</a>
</dt>
<dt>
<a href="kernel.rtlnumberofsetbits">RtlNumberOfSetBits</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlNumberOfClearBits routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>