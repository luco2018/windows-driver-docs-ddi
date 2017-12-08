---
UID: NS.WDM._KEY_VALUE_BASIC_INFORMATION
title: _KEY_VALUE_BASIC_INFORMATION
author: windows-driver-content
description: The KEY_VALUE_BASIC_INFORMATION structure defines a subset of the full information available for a value entry of a registry key.
old-location: kernel\key_value_basic_information.htm
old-project: kernel
ms.assetid: b3b14c21-3613-4f84-9e7d-368c4cc3fa9d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _KEY_VALUE_BASIC_INFORMATION, *PKEY_VALUE_BASIC_INFORMATION, KEY_VALUE_BASIC_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KEY_VALUE_BASIC_INFORMATION
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _KEY_VALUE_BASIC_INFORMATION structure



## -description
The <b>KEY_VALUE_BASIC_INFORMATION</b> structure defines a subset of the full information available for a value entry of a registry key. 


## -syntax

````
typedef struct _KEY_VALUE_BASIC_INFORMATION {
  ULONG TitleIndex;
  ULONG Type;
  ULONG NameLength;
  WCHAR Name[1];
} KEY_VALUE_BASIC_INFORMATION, *PKEY_VALUE_BASIC_INFORMATION;
````


## -struct-fields

### -field TitleIndex

Device and intermediate drivers should ignore this member.

### -field Type

Specifies the system-defined type for the value entry in the registry key, which is one of the following:
<table>
<tr>
<th>REG_<i>XXX</i> type</th>
<th>Value</th>
</tr>
<tr>
<td>
REG_BINARY
</td>
<td>
Binary data in any form
</td>
</tr>
<tr>
<td>
REG_DWORD
</td>
<td>
A 4-byte numerical value
</td>
</tr>
<tr>
<td>
REG_DWORD_LITTLE_ENDIAN
</td>
<td>
A 4-byte numerical value whose least significant byte is at the lowest address
</td>
</tr>
<tr>
<td>
REG_DWORD_BIG_ENDIAN
</td>
<td>
A 4-byte numerical  value whose least significant byte is at the highest address
</td>
</tr>
<tr>
<td>
REG_EXPAND_SZ
</td>
<td>
A null-terminated Unicode string, containing unexpanded references to environment variables, such as "%PATH%"
</td>
</tr>
<tr>
<td>
REG_LINK
</td>
<td>
A Unicode string naming a symbolic link. This type is irrelevant to device and intermediate drivers
</td>
</tr>
<tr>
<td>
REG_MULTI_SZ
</td>
<td>
An array of null-terminated strings, terminated by another zero
</td>
</tr>
<tr>
<td>
REG_NONE
</td>
<td>
Data with no particular type
</td>
</tr>
<tr>
<td>
REG_SZ
</td>
<td>
A null-terminated Unicode string
</td>
</tr>
<tr>
<td>
REG_RESOURCE_LIST
</td>
<td colspan="2">
A device driver's list of hardware resources, used by the driver or one of the physical devices it controls, in the <b>\ResourceMap</b> tree
</td>
</tr>
<tr>
<td>
REG_RESOURCE_REQUIREMENTS_LIST
</td>
<td colspan="2">
A device driver's list of possible hardware resources it or one of the physical devices it controls can use, from which the system writes a subset into the <b>\ResourceMap</b> tree
</td>
</tr>
<tr>
<td>
REG_FULL_RESOURCE_DESCRIPTOR
</td>
<td colspan="2">
A list of hardware resources that a physical device is using, detected and written into the <b>\HardwareDescription</b> tree by the system
</td>
</tr>
</table>
 

### -field NameLength

Specifies the size in bytes of the following value entry name.

### -field Name

A string of Unicode characters naming a value entry of the key.

## -remarks
A kernel-mode driver can obtain a <b>KEY_VALUE_BASIC_INFORMATION</b> that describes a registry key by calling the <a href="kernel.zwqueryvaluekey">ZwQueryValueKey</a> or <a href="kernel.zwenumeratevaluekey">ZwEnumerateValueKey</a> routine.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.key_value_full_information">KEY_VALUE_FULL_INFORMATION</a>
</dt>
<dt>
<a href="kernel.key_value_information_class">KEY_VALUE_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.key_value_partial_information">KEY_VALUE_PARTIAL_INFORMATION</a>
</dt>
<dt>
<a href="kernel.zwenumeratevaluekey">ZwEnumerateValueKey</a>
</dt>
<dt>
<a href="kernel.zwqueryvaluekey">ZwQueryValueKey</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KEY_VALUE_BASIC_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>