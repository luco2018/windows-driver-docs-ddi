---
UID: NS.ntddk._WHEA_GENERIC_ERROR_DESCRIPTOR
title: WHEA_GENERIC_ERROR_DESCRIPTOR
author: windows-driver-content
description: The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.
old-location: whea\whea_generic_error_descriptor.htm
old-project: whea
ms.assetid: a3ab6522-8706-4166-974f-1744b352f3c2
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_GENERIC_ERROR_DESCRIPTOR, WHEA_GENERIC_ERROR_DESCRIPTOR, *PWHEA_GENERIC_ERROR_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WHEA_GENERIC_ERROR_DESCRIPTOR
req.alt-loc: ntddk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# WHEA_GENERIC_ERROR_DESCRIPTOR structure



## -description
<p>The WHEA_GENERIC_ERROR_DESCRIPTOR structure describes a generic error source.</p>


## -syntax

````
typedef struct _WHEA_GENERIC_ERROR_DESCRIPTOR {
  USHORT                       Type;
  UCHAR                        Reserved;
  UCHAR                        Enabled;
  ULONG                        ErrStatusBlockLength;
  ULONG                        RelatedErrorSourceId;
  UCHAR                        ErrStatusAddressSpaceID;
  UCHAR                        ErrStatusAddressBitWidth;
  UCHAR                        ErrStatusAddressBitOffset;
  UCHAR                        ErrStatusAddressAccessSize;
  WHEA_PHYSICAL_ADDRESS        ErrStatusAddress;
  WHEA_NOTIFICATION_DESCRIPTOR Notify;
} WHEA_GENERIC_ERROR_DESCRIPTOR, *PWHEA_GENERIC_ERROR_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field Type

<dd>
<p>The type of error source descriptor. This member is always set to WHEA_ERROR_SOURCE_DESCRIPTOR_TYPE_GENERIC.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Enabled

<dd>
<p>A Boolean value that indicates if the error source is enabled.</p>
</dd>

### -field ErrStatusBlockLength

<dd>
<p>The size, in bytes, of the block of error status registers that contain the error data for the error source.</p>
</dd>

### -field RelatedErrorSourceId

<dd>
<p>The identifier of the related error source. If the generic error source does not relate back to another error source, this member is not used.</p>
</dd>

### -field ErrStatusAddressSpaceID

<dd>
<p>The address space of the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:</p>
<p></p>
<dl>

### -field 0x00

<dd>
<p>System memory space</p>
</dd>

### -field 0x01

<dd>
<p>System I/O space</p>
</dd>

### -field 0x02

<dd>
<p>PCI configuration space</p>
</dd>

### -field 0x03

<dd>
<p>Embedded controller address space</p>
</dd>

### -field 0x04

<dd>
<p>System management bus (SMBus) address space</p>
</dd>

### -field 0x05 - 0x7E

<dd>
<p>Reserved</p>
</dd>

### -field 0x7F

<dd>
<p>Functional fixed hardware address space</p>
</dd>

### -field 0x80 - 0xBF

<dd>
<p>Reserved</p>
</dd>

### -field 0xC0 - 0xFF

<dd>
<p>OEM defined address space</p>
</dd>
</dl>
</dd>

### -field ErrStatusAddressBitWidth

<dd>
<p>The size, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.</p>
</dd>

### -field ErrStatusAddressBitOffset

<dd>
<p>The offset, in bits, of the register at the address that is specified in the <b>ErrStatusAddress</b> member.</p>
</dd>

### -field ErrStatusAddressAccessSize

<dd>
<p>The access size for reading the register at the address that is specified in the <b>ErrStatusAddress</b> member. Possible values are:</p>
<p></p>
<dl>

### -field 0

<dd>
<p>Undefined</p>
</dd>

### -field 1

<dd>
<p>Byte access</p>
</dd>

### -field 2

<dd>
<p>Word access</p>
</dd>

### -field 3

<dd>
<p>Double word access</p>
</dd>

### -field 4

<dd>
<p>Quad word access</p>
</dd>
</dl>
</dd>

### -field ErrStatusAddress

<dd>
<p>The 64-bit address of a register that contains the physical address of a block of memory that contains the error status data for the error source. This block of memory must reside in firmware reserved memory so that it is not reclaimed by the operating system's memory manager. The error status data contained in this block of memory is described by a <a href="..\ntddk\ns-ntddk--whea-generic-error.md">WHEA_GENERIC_ERROR</a> structure.</p>
</dd>

### -field Notify

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-notification-descriptor.md">WHEA_NOTIFICATION_DESCRIPTOR</a> structure that describes the notification mechanism that is used by the error source.</p>
</dd>
</dl>

## -remarks
<p>A WHEA_GENERIC_ERROR_DESCRIPTOR structure is contained within the <a href="..\ntddk\ns-ntddk--whea-error-source-descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a> structure.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-source-descriptor.md">WHEA_ERROR_SOURCE_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-generic-error.md">WHEA_GENERIC_ERROR</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-notification-descriptor.md">WHEA_NOTIFICATION_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_GENERIC_ERROR_DESCRIPTOR structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>