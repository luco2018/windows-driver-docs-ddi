---
UID: NF.dbgeng.IDebugSystemObjects.GetThreadIdByTeb
title: IDebugSystemObjects::GetThreadIdByTeb
author: windows-driver-content
description: The GetThreadIdByTeb method returns the engine thread ID of the specified thread. The thread is specified by its thread environment block (TEB).
old-location: debugger\getthreadidbyteb.htm
old-project: debugger
ms.assetid: 64b98d8b-883b-4a2c-a5de-058bb3b732df
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSystemObjects, GetThreadIdByTeb, IDebugSystemObjects::GetThreadIdByTeb
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
req.alt-api: IDebugSystemObjects.GetThreadIdByTeb,IDebugSystemObjects2.GetThreadIdByTeb,IDebugSystemObjects3.GetThreadIdByTeb,IDebugSystemObjects4.GetThreadIdByTeb
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
req.iface: IDebugSystemObjects
---

# IDebugSystemObjects::GetThreadIdByTeb method



## -description
<p>The <b>GetThreadIdByTeb</b> method returns the engine thread ID of the specified thread.  The thread is specified by its thread environment block (TEB).</p>


## -syntax

````
HRESULT GetThreadIdByTeb(
  [in]  ULONG64 Offset,
  [out] PULONG  Id
);
````


## -parameters
<dl>

### -param Offset [in]

<dd>
<p>Specifies the location of the thread's TEB.</p>
</dd>

### -param Id [out]

<dd>
<p>Receives the engine thread ID.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>In kernel-mode debugging, this method returns the engine thread ID for the virtual thread representing the processor on which the specified thread is executing.  If the thread is not executing on a processor, this method will fail.</p>

<p>For more information about threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558896">Threads and Processes</a>.</p>

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