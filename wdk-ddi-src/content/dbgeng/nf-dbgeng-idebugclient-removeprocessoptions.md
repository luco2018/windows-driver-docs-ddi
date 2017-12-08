---
UID: NF.dbgeng.IDebugClient.RemoveProcessOptions
title: IDebugClient::RemoveProcessOptions
author: windows-driver-content
description: The RemoveProcessOptions method removes process options from those options that affect the current process.
old-location: debugger\removeprocessoptions.htm
old-project: debugger
ms.assetid: 8b2cf167-d1bd-440e-beb4-5159b8b13073
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugClient, RemoveProcessOptions, IDebugClient::RemoveProcessOptions
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
req.alt-api: IDebugClient.RemoveProcessOptions,IDebugClient2.RemoveProcessOptions,IDebugClient3.RemoveProcessOptions,IDebugClient4.RemoveProcessOptions,IDebugClient5.RemoveProcessOptions
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
req.iface: IDebugClient
---

# IDebugClient::RemoveProcessOptions method



## -description
<p>The <b>RemoveProcessOptions</b> method removes process options from those options that affect the current process.</p>


## -syntax

````
HRESULT RemoveProcessOptions(
  [in] ULONG Options
);
````


## -parameters
<dl>

### -param Options [in]

<dd>
<p>Specifies the process options to remove from those affecting the current process.  For details on these options, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>This method is available only in live user-mode debugging.</p>

<p>Some of the process options are global options, others are specific to the current process.</p>

<p>If any process options are modified, the engine will notify the event callbacks by calling their <a href="debugger.idebugeventcallbacks_changeenginestate">IDebugEventCallbacks::ChangeEngineState</a> method with the DEBUG_CES_PROCESS_OPTIONS flag set.</p>

<p>For more information about creating and attaching to live user-mode targets, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552020">Live User-Mode Targets</a>.</p>

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

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient.md">IDebugClient</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient2.md">IDebugClient2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient3.md">IDebugClient3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient4.md">IDebugClient4</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="debugger.getprocessoptions">GetProcessOptions</a>
</dt>
<dt>
<a href="debugger.setprocessoptions">SetProcessOptions</a>
</dt>
<dt>
<a href="debugger.addprocessoptions">AddProcessOptions</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff541534">DEBUG_PROCESS_XXX</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient::RemoveProcessOptions method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>