---
UID: NS.usbbusif._USBC_FUNCTION_DESCRIPTOR
title: USBC_FUNCTION_DESCRIPTOR
author: windows-driver-content
description: The USBC_FUNCTION_DESCRIPTOR structure describes a USB function and its associated interface collection.
old-location: buses\usbc_function_descriptor.htm
old-project: usbref
ms.assetid: 43ac738b-7837-4183-ad06-5c35a2af38ff
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: USBC_FUNCTION_DESCRIPTOR, USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbbusif.h
req.include-header: Usbbusif.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBC_FUNCTION_DESCRIPTOR
req.alt-loc: usbbusif.h
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

# USBC_FUNCTION_DESCRIPTOR structure



## -description
<p>The <b>USBC_FUNCTION_DESCRIPTOR</b> structure describes a USB function and its associated interface collection.</p>


## -syntax

````
typedef struct _USBC_FUNCTION_DESCRIPTOR {
  UCHAR                     FunctionNumber;
  UCHAR                     NumberOfInterfaces;
  PUSB_INTERFACE_DESCRIPTOR *InterfaceDescriptorList;
  UNICODE_STRING            HardwareId;
  UNICODE_STRING            CompatibleId;
  UNICODE_STRING            FunctionDescription;
  ULONG                     FunctionFlags;
  PVOID                     Reserved;
} USBC_FUNCTION_DESCRIPTOR, *PUSBC_FUNCTION_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field FunctionNumber

<dd>
<p>The zero-based index of the interface collection.</p>
</dd>

### -field NumberOfInterfaces

<dd>
<p>The number of interfaces in the interface collection.</p>
</dd>

### -field InterfaceDescriptorList

<dd>
<p>An array of pointers to <a href="..\usbspec\ns-usbspec--usb-interface-descriptor.md">USB_INTERFACE_DESCRIPTOR</a>-type structures that describe the interfaces in the interface collection.</p>
</dd>

### -field HardwareId

<dd>
<p>The hardware identifier of the interface collection.</p>
</dd>

### -field CompatibleId

<dd>
<p>The compatible identifier of the interface collection.</p>
</dd>

### -field FunctionDescription

<dd>
<p>A description of the interface collection in human-readable text.</p>
</dd>

### -field FunctionFlags

<dd>
<p>Vendor-defined flags that describe the interface collection.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved.</p>
</dd>
</dl>

## -remarks
<p>For information on how to use user-defined callback routines to provide a custom definition of the interface collections on a device, see <a href="buses.custom_enumeration_of_interface_collections_by_vendor_supplied_callbac">Customizing Enumeration of Interface Collections for Composite Devices</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Usbbusif.h (include Usbbusif.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbspec\ns-usbspec--usb-interface-descriptor.md">USB_INTERFACE_DESCRIPTOR</a>
</dt>
<dt>
<a href="buses.usb_structures_and_enumerations">USB Structures</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBC_FUNCTION_DESCRIPTOR structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>