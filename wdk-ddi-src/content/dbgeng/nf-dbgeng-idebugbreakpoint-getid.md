---
UID: NF.dbgeng.IDebugBreakpoint.GetId
title: IDebugBreakpoint::GetId
author: windows-driver-content
description: The GetId method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.
old-location: debugger\getid.htm
old-project: debugger
ms.assetid: 991d8a40-1991-4c06-9557-9abee3ed8073
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugBreakpoint, GetId, IDebugBreakpoint::GetId
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
req.alt-api: IDebugBreakpoint.GetId,IDebugBreakpoint2.GetId
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

# IDebugBreakpoint::GetId method



## -description
<p>The <b>GetId</b> method returns a breakpoint ID, which is the engine's unique identifier for a breakpoint.</p>


## -syntax

````
HRESULT GetId(
  [out] PULONG Id
);
````


## -parameters
<dl>

### -param Id [out]

<dd>
<p>The breakpoint ID.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.</p>

## -remarks
<p>The breakpoint ID remains fixed as long as the breakpoint exists.  However, after the breakpoint has been removed, you can use its ID for another breakpoint.</p>

<p>The <a href="debugger.getparameters">GetParameters</a> method also returns the breakpoint ID.</p>

<p>For more information about how to use breakpoints, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560075">Using Breakpoints</a>.</p>

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