---
UID: NF.dbgeng.IDebugDataSpaces4.WriteControl
title: IDebugDataSpaces4::WriteControl
author: windows-driver-content
description: The WriteControl method writes implementation-specific system data.
old-location: debugger\writecontrol.htm
old-project: debugger
ms.assetid: 0b512c66-7cd8-4605-87d5-13b78d790c8c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugDataSpaces4, WriteControl, IDebugDataSpaces4::WriteControl
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
req.alt-api: IDebugDataSpaces.WriteControl,IDebugDataSpaces2.WriteControl,IDebugDataSpaces3.WriteControl,IDebugDataSpaces4.WriteControl
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
req.iface: IDebugDataSpaces4
---

# IDebugDataSpaces4::WriteControl method



## -description
<p>The <b>WriteControl</b> method writes implementation-specific system data.</p>


## -syntax

````
HRESULT WriteControl(
  [in]            ULONG   Processor,
  [in]            ULONG64 Offset,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````


## -parameters
<dl>

### -param Processor [in]

<dd>
<p>Specifies the processor whose information is to be written.</p>
</dd>

### -param Offset [in]

<dd>
<p>Specifies the offset of the control space of the memory to write.</p>
</dd>

### -param Buffer [in]

<dd>
<p>Specifies the data to write to the control-space memory.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.</p>
</dd>

### -param BytesWritten [out, optional]

<dd>
<p>Receives the number of bytes returned in the buffer <i>Buffer</i>.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>This method is only available in kernel-mode debugging.</p>

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