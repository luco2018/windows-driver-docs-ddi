---
UID: NF.ndis.NdisUnicodeStringToAnsiString
title: NdisUnicodeStringToAnsiString
author: windows-driver-content
description: The NdisUnicodeStringToAnsiString function converts a given counted Unicode string into a counted ANSI string. The translation conforms to the current system locale information.
old-location: netvista\ndisunicodestringtoansistring.htm
old-project: netvista
ms.assetid: 37ac55b8-093e-4bf4-9c66-05ab5fc7ebc9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NdisUnicodeStringToAnsiString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use RtlUnicodeStringToAnsiString instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisUnicodeStringToAnsiString
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NdisUnicodeStringToAnsiString function



## -description
<p>The 
  <b>NdisUnicodeStringToAnsiString</b> function converts a given counted Unicode string into a counted ANSI
  string. The translation conforms to the current system locale information.</p>


## -syntax

````
NDIS_STATUS NdisUnicodeStringToAnsiString(
  _Inout_ PANSI_STRING    DestinationString,
  _In_    PUNICODE_STRING SourceString
);
````


## -parameters
<dl>

### -param DestinationString [in, out]

<dd>
<p>A pointer to a caller-allocated buffer in which this function should return the converted ANSI
     string.</p>
</dd>

### -param SourceString [in]

<dd>
<p>A pointer to the Unicode string to be converted.</p>
</dd>
</dl>

## -returns
<p><b>NdisUnicodeStringToAnsiString</b> returns NDIS_STATUS_SUCCESS if the conversion succeeds. Otherwise,
     the contents of the buffer at 
     <i>DestinationString</i> are unaffected.</p>

## -remarks
<p>The caller must allocate storage for both the source and destination strings and release these buffers
    as soon as the strings are no longer needed. The buffer at 
    <i>SourceString</i> must be at least twice the size of that at 
    <i>DestinationString</i> .</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for existing drivers in  NDIS 6.0 and later, but new drivers should use <a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a> instead.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_miscellaneous_function">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
<dt>
<a href="netvista.driverentry_of_ndis_protocol_drivers">DriverEntry of NDIS Protocol
   Drivers</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-bind-adapter-ex.md">ProtocolBindAdapterEx</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm--unicode-string.md">UNICODE_STRING</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisUnicodeStringToAnsiString function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>