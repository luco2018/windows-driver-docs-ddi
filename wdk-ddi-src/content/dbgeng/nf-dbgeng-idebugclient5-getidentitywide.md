---
UID: NF.dbgeng.IDebugClient5.GetIdentityWide
title: IDebugClient5::GetIdentityWide
author: windows-driver-content
description: The GetIdentityWide method returns a string describing the computer and user this client represents.
old-location: debugger\getidentitywide.htm
old-project: debugger
ms.assetid: 8e55f829-2f55-4b83-8e0d-2554246a5d59
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IDebugClient5, GetIdentityWide, IDebugClient5::GetIdentityWide
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
req.alt-api: IDebugClient5.GetIdentityWide
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
req.iface: IDebugClient5
---

# IDebugClient5::GetIdentityWide method



## -description
<p>The <b>GetIdentityWide</b> method returns a string describing the computer and user this client represents.</p>


## -syntax

````
HRESULT GetIdentityWide(
  [out, optional] PWSTR  Buffer,
  [in]            ULONG  BufferSize,
  [out, optional] PULONG IdentitySize
);
````


## -parameters
<dl>

### -param Buffer [out, optional]

<dd>
<p>Specifies the buffer to receive the string.  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.</p>
</dd>

### -param BufferSize [in]

<dd>
<p>Specifies the size of the buffer <i>Buffer</i>.</p>
</dd>

### -param IdentitySize [out, optional]

<dd>
<p>Receives the size of the string. If <i>IdentitySize</i> is <b>NULL</b>, this information is not returned.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful</p><dl>
<dt><b>S_FALSE</b></dt>
</dl><p>The size of the string was greater than the size of the buffer, so it was truncated to fit into the buffer.</p>

<p> </p>

## -remarks
<p>The specific content of the string varies with the operating system.  If the client is remotely connected, some network information may also be present.</p>

<p>For more information about client objects, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539140">Client Objects</a>.</p>

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
<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>
</dt>
<dt>
<a href="debugger.outputidentity">OutputIdentity</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugClient5::GetIdentityWide method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>