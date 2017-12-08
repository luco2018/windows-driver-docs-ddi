---
UID: NF.extsfns.IDebugFailureAnalysis2.AddUlong64
title: IDebugFailureAnalysis2::AddUlong64
author: windows-driver-content
description: The AddUlong64 method adds a new FA entry to a DebugFailureAnalysis object and sets the data block of the FA entry to a specified 64-bit value.
old-location: debugger\idebugfailureanalysis2_addulong64.htm
old-project: debugger
ms.assetid: E5FB5911-C6E5-44C1-B33F-75B4DD86A3D9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugFailureAnalysis2, AddUlong64, IDebugFailureAnalysis2::AddUlong64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: extsfns.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugFailureAnalysis2.AddUlong64
req.alt-loc: extsfns.h
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
req.iface: IDebugFailureAnalysis2
---

# IDebugFailureAnalysis2::AddUlong64 method



## -description
<p>The <b>AddUlong64</b> method adds a new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>  to a <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">DebugFailureAnalysis</a> object and sets the data block of the FA entry to a specified 64-bit value.</p>


## -syntax

````
PFA_ENTRY AddUlong64(
       FA_TAG  Tag,
  [in] ULONG64 Value
);
````


## -parameters
<dl>

### -param Tag 

<dd>
<p>A value in the <a href="https://msdn.microsoft.com/library/windows/hardware/jj991810">FA_TAG</a> enumeration. The data type associated with this tag must be <b>DEBUG_FA_ENTRY_ULONG64</b> or <b>DEBUG_FA_ENTRY_POINTER</b> or <b>DEBUG_FA_ENTRY_INSTRUCTION_OFFSET</b>.
</p>
</dd>

### -param Value [in]

<dd>
<p>The <b>ULONG64</b> value to be written to the data block of the new <a href="https://msdn.microsoft.com/759DE159-F2A8-4BB1-AAF5-B2B91C4F91B0">FA entry</a>.</p>
</dd>
</dl>

## -returns
<p>If this method succeeds, it returns a returns a pointer to the new <a href="..\extsfns\ns-extsfns--fa-entry.md">FA_ENTRY</a> structure. If this method fails, it returns <b>NULL</b>.</p>

## -remarks
<p>Each tag is associated with one of the data types in the <a href="..\extsfns\ne-extsfns--fa-entry-type.md">FA_ENTRY_TYPE</a> enumeration. To determine the data type associated with a tag, call the <a href="debugger.idebugfaentrytags_gettype">GetType</a> method of the <a href="debugger.idebugfaentrytags">IDebugFAEntryTags</a> interface.</p>

<p>To get a pointer to an <a href="debugger.idebugfaentrytags">IDebugFAEntryTags</a> interface, call the <a href="debugger.idebugfailureanalysis2_getdebugfatagcontrol">GetDebugFATagControl</a> method of the <a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a> interface. </p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Extsfns.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\extsfns\nn-extsfns-idebugfailureanalysis2.md">IDebugFailureAnalysis2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7648F789-85D5-4247-90DD-2EAA43543483">Writing an Analysis Extension Plug-in to Extend !analyze</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_getulong64">GetUlong64</a>
</dt>
<dt>
<a href="debugger.idebugfailureanalysis2_setulong64">SetUlong64</a>
</dt>
<dt>
<a href="debugger._efn_analyze">_EFN_Analyze</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugFailureAnalysis2::AddUlong64 method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>