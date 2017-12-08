---
UID: NF.dbgeng.IDebugSymbols.AddSymbolOptions
title: IDebugSymbols::AddSymbolOptions
author: windows-driver-content
description: The AddSymbolOptions method turns on some of the engine's global symbol options.
old-location: debugger\addsymboloptions.htm
old-project: debugger
ms.assetid: 952b4a7b-2713-4d7a-b70e-4fd1867bc096
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugSymbols, AddSymbolOptions, IDebugSymbols::AddSymbolOptions
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h, Dbghelp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.AddSymbolOptions,IDebugSymbols2.AddSymbolOptions,IDebugSymbols3.AddSymbolOptions
req.alt-loc: Dbgeng.h
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
req.iface: IDebugSymbols
---

# IDebugSymbols::AddSymbolOptions method



## -description
<p>The <b>AddSymbolOptions</b> method turns on some of the engine's global symbol options.</p>


## -syntax

````
HRESULT AddSymbolOptions(
  [in] PULONG Options
);
````


## -parameters
<dl>

### -param Options [in]

<dd>
<p>Specifies the symbol options to turns on.  <i>Options</i> is a bit-set that will be ORed with the existing symbol options.  For a description of the bit flags, see <a href="https://msdn.microsoft.com/4a501ea3-431c-4c11-8826-154eb8799a64">Setting Symbol Options</a>.</p>
</dd>
</dl>

## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p>

## -remarks
<p>After the symbol options have been changed, for each client the engine sends out notification to that client's <a href="..\dbgeng\nn-dbgeng-idebugeventcallbacks.md">IDebugEventCallbacks</a> by passing the DEBUG_CES_SYMBOL_OPTIONS flag to the <a href="debugger.idebugeventcallbacks_changesymbolstate">IDebugEventCallbacks::ChangeSymbolState</a> method.</p>

<p>For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.</p>

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
<dt>Dbgeng.h (include Dbgeng.h or Dbghelp.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.getsymboloptions">GetSymbolOptions</a>
</dt>
<dt>
<a href="debugger.removesymboloptions">RemoveSymbolOptions</a>
</dt>
<dt>
<a href="debugger.setsymboloptions">SetSymbolOptions</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::AddSymbolOptions method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>