---
UID: NF.ntstrsafe.RtlStringCbCopyNA
title: RtlStringCbCopyNA
author: windows-driver-content
description: The RtlStringCbCopyNW and RtlStringCbCopyNA functions copy a byte-counted string to a buffer while limiting the size of the copied string.
old-location: kernel\rtlstringcbcopyn.htm
old-project: kernel
ms.assetid: d64fb3e6-fba1-4383-bdb0-a63dc7c16033
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlStringCbCopyNA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlStringCbCopyN,RtlStringCbCopyNA,RtlStringCbCopyNW
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: RtlStringCbCopyNW (Unicode) and RtlStringCbCopyNA (ANSI)
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# RtlStringCbCopyNA function



## -description
<p>The <b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> functions copy a byte-counted string to a buffer while limiting the size of the copied string.</p>


## -syntax

````
NTSTATUS RtlStringCbCopyN(
  _Out_ LPTSTR  pszDest,
  _In_  size_t  cbDest,
  _In_  LPCTSTR pszSrc,
  _In_  size_t  cbSrc
);
````


## -parameters
<dl>

### -param pszDest [out]

<dd>
<p>A pointer to a caller-supplied buffer that receives the copied string. The string at <i>pszSrc</i>, up to <i>cbSrc</i> bytes, is copied to the buffer at <i>pszDest</i> and terminated with a null character. </p>
</dd>

### -param cbDest [in]

<dd>
<p>The size, in bytes, of the destination buffer. The buffer must be large enough for both the string and the terminating null character.</p>
<p>For Unicode strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(WCHAR). </p>
<p>For ANSI strings, the maximum number of bytes is NTSTRSAFE_MAX_CCH * <b>sizeof</b>(<b>char</b>). </p>
</dd>

### -param pszSrc [in]

<dd>
<p>A pointer to a caller-supplied, null-terminated string. </p>
</dd>

### -param cbSrc [in]

<dd>
<p>The maximum number of bytes to copy from <i>pszSrc</i> to <i>pszDest</i>.</p>
</dd>
</dl>

## -returns
<p>The function returns one of the NTSTATUS values that are listed in the following table. For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>This <i>success</i> status means source data was present, the string was copied without truncation, and the resultant destination buffer is null-terminated.</p><dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl><p>This <i>warning</i> status means the copy operation did not complete due to insufficient space in the destination buffer. The destination buffer contains a truncated version of the copied string.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>This <i>error</i> status means the function received an invalid input parameter. For more information, see the following paragraph.</p>

<p>The function returns the STATUS_INVALID_PARAMETER value when:</p>

<p> </p>

## -remarks
<p><b>RtlStringCbCopyNW</b> and <b>RtlStringCbCopyNA</b> should be used instead of <b>strncpy</b>. However, these functions  differ in behavior. If <i>cbSrc</i> is larger than the number of bytes in <i>pszSrc</i>, the <b>RtlStringCbCopyN </b>functions—unlike <b>strncpy</b>—do not fill <i>pszDest</i> with null characters until <i>cbSrc</i> bytes have been copied.</p>

<p><b>RtlStringCbCopyN</b> copies a given number of bytes from a source string. The size, in bytes, of the destination buffer is provided to the function to ensure that <b>RtlStringCbCopyN</b> does not write past the end of this buffer.</p>

<p>Use <b>RtlStringCbCopyNW</b> to handle Unicode strings and <b>RtlStringCbCopyNA</b> to handle ANSI strings. The form you use depends on your data, as shown in the following table.</p>

<p>WCHAR</p>

<p>L"string"</p>

<p><b>RtlStringCbCopyNW</b></p>

<p><b>char</b></p>

<p>"string"</p>

<p><b>RtlStringCbCopyNA</b></p>

<p>If <i>pszSrc</i> and <i>pszDest</i> point to overlapping strings, the behavior of the function is undefined.</p>

<p>Neither <i>pszSrc</i> nor <i>pszDest</i> can be <b>NULL</b>. If you need to handle <b>NULL</b> string pointer values, see <a href="kernel.rtlstringcbcopynex">RtlStringCbCopyNEx</a>.</p>

<p>For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.h (include Ntstrsafe.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.lib</dt>
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
<p>Unicode and ANSI names</p>
</th>
<td width="70%">
<p><b>RtlStringCbCopyNW</b> (Unicode) and <b>RtlStringCbCopyNA</b> (ANSI)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlstringcbcopy">RtlStringCbCopy</a>
</dt>
<dt>
<a href="kernel.rtlstringcchcopyn">RtlStringCchCopyN</a>
</dt>
<dt>
<a href="kernel.rtlstringcbcopynex">RtlStringCbCopyNEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlStringCbCopyN function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>