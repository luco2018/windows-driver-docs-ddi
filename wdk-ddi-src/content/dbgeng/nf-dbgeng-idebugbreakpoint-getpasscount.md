---
UID: NF.dbgeng.IDebugBreakpoint.GetPassCount
title: IDebugBreakpoint::GetPassCount
author: windows-driver-content
description: The GetPassCount method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.
old-location: debugger\getpasscount.htm
old-project: debugger
ms.assetid: d7abe2aa-a33c-4184-a850-d0efa1e99221
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugBreakpoint, GetPassCount, IDebugBreakpoint::GetPassCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugBreakpoint.GetPassCount,IDebugBreakpoint2.GetPassCount
req.alt-loc: dbgeng.h
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
req.iface: IDebugBreakpoint
---

# IDebugBreakpoint::GetPassCount method



## -description
<p>The <b>GetPassCount</b> method returns the number of times that the target was originally required to reach the breakpoint location before the breakpoint is triggered.</p>


## -syntax

````
HRESULT GetPassCount(
  [out] PULONG Count
);
````


## -parameters
<dl>

### -param Count [out]

<dd>
<p>The number of times that the target was originally required to hit the breakpoint before it is triggered.  The number of times that the target was originally required to pass the breakpoint without triggering it is the value that is returned to <i>Count</i>, minus one.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.</p>

## -remarks
<p>The <b>GetPassCount</b> method returns the number of hits that were originally required to trigger the breakpoint. The <a href="debugger.getcurrentpasscount">GetCurrentPassCount</a> method returns the number of hits that still must occur to trigger the breakpoint. For example, if a breakpoint was created with a pass count of 20, and there have been 5 passes so far, this method <b>GetPassCount</b> returns 20 and <b>GetCurrentPassCount</b> returns 15.</p>

<p>After the target has hit the breakpoint enough times to trigger it, the breakpoint is triggered every time that it is hit, unless you call <a href="debugger.setpasscount">SetPassCount</a>.  You can also call <b>SetPassCount</b> to change the pass count before the breakpoint has been triggered. This call resets the original pass count and the remaining pass count.</p>

<p>If the debugger executes the code at the breakpoint location while stepping through the code, this execution does not contribute to the number of times that remain before the breakpoint is triggered.</p>

<p>The <a href="debugger.getparameters">GetParameters</a> method also returns the information that is returned in <i>Count</i>.</p>

<p>For more information about breakpoint properties, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539284">Controlling Breakpoint Flags and Parameters</a>.</p>

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
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>