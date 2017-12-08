---
UID: NF.wdbgexts.GetKdContext
title: GetKdContext
author: windows-driver-content
description: The GetKdContext function returns the total number of processors and the number of the current processor in the structure ppi points to.
old-location: debugger\getkdcontext.htm
old-project: debugger
ms.assetid: cf795629-cf62-45fa-ad5e-e2eef576bcfd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: GetKdContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GetKdContext
req.alt-loc: wdbgexts.h
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
req.product: Windows 10 or later.
---

# GetKdContext function



## -description
<p>The <b>GetKdContext</b> function returns the total number of processors and the number of the current processor in the structure <i>ppi</i> points to.</p>


## -syntax

````
ULONG GetKdContext(
   PPROCESSORINFO ppi
);
````


## -parameters
<dl>

### -param ppi 

<dd>
<p>Points to the following structure:</p>
<pre class="syntax" xml:space="preserve"><code>typedef struct _tagPROCESSORINFO {
  USHORT  Processor;           // current processor
  USHORT  NumberProcessors;    // total number of processors
} PROCESSORINFO, *PPROCESSORINFO;</code></pre>
</dd>
</dl>

## -returns
<p>The total number of processors.</p>

## -remarks


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
<dt>Wdbgexts.h (include Wdbgexts.h or Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>