---
UID: NF.ntintsafe.RtlULongToChar
title: RtlULongToChar function
author: windows-driver-content
description: Converts a value of type ULONG to a value of type CHAR.
old-location: kernel\rtlulongtochar.htm
old-project: kernel
ms.assetid: 43BD3798-0FCA-4A44-8EE1-DE252636CC95
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlULongToChar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlULongToChar
req.alt-loc: Ntintsafe.h
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
---

# RtlULongToChar function



## -description
Converts a value of type <b>ULONG</b> to a value of type <b>CHAR</b>.


## -syntax

````
NTSTATUS RtlULongToChar(
  _In_  ULONG ulOperand,
  _Out_ CHAR  *pch
);
````


## -parameters

### -param ulOperand [in]

The value to be converted.

### -param pch [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.

## -remarks
This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntintsafe.h</dt>
</dl>
</td>
</tr>
</table>