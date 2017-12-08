---
UID: NS.acpiioct._ACPI_GET_DEVICE_SPECIFIC_DATA
title: ACPI_GET_DEVICE_SPECIFIC_DATA
author: windows-driver-content
description: The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.
old-location: acpi\acpi_get_device_specific_data.htm
old-project: acpi
ms.assetid: F7B4E80F-AB83-4E0F-9933-D953744A1970
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ACPI_GET_DEVICE_SPECIFIC_DATA, ACPI_GET_DEVICE_SPECIFIC_DATA, *PACPI_GET_DEVICE_SPECIFIC_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: acpiioct.h
req.include-header: Acpiioct.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ACPI_GET_DEVICE_SPECIFIC_DATA
req.alt-loc: Acpiioct.h
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

# ACPI_GET_DEVICE_SPECIFIC_DATA structure



## -description
<p>The ACPI_GET_DEVICE_SPECIFIC_DATA structure contains input arguments for the IOCTL_ACPI_GET_DEVICE_SPECIFIC_DATA control method.</p>


## -syntax

````
typedef struct _ACPI_GET_DEVICE_SPECIFIC_DATA {
  ULONG Signature;
  GUID  Section;
  ULONG PropertyNameLength;
  UCHAR PropertyName[ANYSIZE_ARRAY];
} ACPI_GET_DEVICE_SPECIFIC_DATA, *PACPI_GET_DEVICE_SPECIFIC_DATA;
````


## -struct-fields
<dl>

### -field Signature

<dd>
<p>A unique identifier for the IOCTL.</p>
</dd>

### -field Section

<dd>
<p>A GUID specified by the caller.</p>
</dd>

### -field PropertyNameLength

<dd>
<p>The length of the property name.</p>
</dd>

### -field PropertyName

<dd>
<p>Specifies the property name. If not specified, the <b>PropertyNameLength</b> and the <b>PropertyName</b> are returned. If a <b>PropertyName</b> is specified, only the value of that <b>PropertyName</b> is returned.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Acpiioct.h (include Acpiioct.h)</dt>
</dl>
</td>
</tr>
</table>