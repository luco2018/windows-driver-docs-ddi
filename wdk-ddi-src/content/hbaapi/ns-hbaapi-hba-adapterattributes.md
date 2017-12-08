---
UID: NS.hbaapi.HBA_AdapterAttributes
title: HBA_AdapterAttributes
author: windows-driver-content
description: The HBA_AdapterAttributes structure is used in conjunction with the HBA_GetAdapterAttributes routine to report the attributes of an HBA.
old-location: storage\hba_adapterattributes.htm
old-project: storage
ms.assetid: d86a5810-7014-41d5-bd88-3a1bd50032da
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: HBA_AdapterAttributes, HBA_ADAPTERATTRIBUTES, *PHBA_ADAPTERATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HBA_ADAPTERATTRIBUTES
req.alt-loc: hbaapi.h
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
---

# HBA_AdapterAttributes structure



## -description
<p>The HBA_AdapterAttributes structure is used in conjunction with the <a href="..\hbaapi\nf-hbaapi-hba-getadapterattributes.md">HBA_GetAdapterAttributes</a> routine to report the attributes of an HBA.</p>


## -syntax

````
typedef struct HBA_AdapterAttributes {
  char       Manufacturer[64];
  char       SerialNumber[64];
  char       Model[256];
  char       ModelDescription[256];
  HBA_WWN    NodeWWN;
  char       NodeSymbolicName[256];
  char       HardwareVersion[256];
  char       DriverVersion[256];
  char       OptionROMVersion[256];
  char       FirmwareVersion[256];
  HBA_UINT32 VendorSpecificID;
  HBA_UINT32 NumberOfPorts;
  char       DriverName[256];
} HBA_ADAPTERATTRIBUTES, *PHBA_ADAPTERATTRIBUTES;
````


## -struct-fields
<dl>

### -field Manufacturer

<dd>
<p>Contains a string not exceeding 64 bytes in length that indicates the name of the manufacturer of the HBA..</p>
</dd>

### -field SerialNumber

<dd>
<p>Contains a string not exceeding 64 bytes in length that indicates the serial number of the HBA. </p>
</dd>

### -field Model

<dd>
<p>Contains a string not exceeding 256 bytes in length that indicates a vendor specific name or identifying text for the HBA model.  </p>
</dd>

### -field ModelDescription

<dd>
<p>Contains a string not exceeding 256 bytes in length that provides a description of the HBA model.</p>
</dd>

### -field NodeWWN

<dd>
<p>Contains the 64 bit world-wide name that indicates the name of the node (machine) that the HBA is located on. If an HBA has multiple ports associated with more than one node, the member will contain a name chosen by vendor-specific means from among the names of the associated nodes. For a discussion of worldwide names, see the T11 committee's <i>Fibre Channel HBA API</i> specification.</p>
</dd>

### -field NodeSymbolicName

<dd>
<p>Contains a string not exceeding 256 bytes in length that indicates the symbolic name of the fibre channel node (machine) that the adapter is located on. </p>
</dd>

### -field HardwareVersion

<dd>
<p>Contains a string not exceeding 256 bytes in length that indicates the hardware revision level of the HBA.</p>
</dd>

### -field DriverVersion

<dd>
<p>Contains a string not exceeding 256 bytes in length that indicates version of the driver that manages the HBA.</p>
</dd>

### -field OptionROMVersion

<dd>
<p>Contains a string not exceeding 256 bytes in length that specifies the option ROM or the version of the BIOS of the HBA. </p>
</dd>

### -field FirmwareVersion

<dd>
<p>Contains a string not exceeding 256 bytes in length that identifies the version of the HBA's firmware.</p>
</dd>

### -field VendorSpecificID

<dd>
<p>Contains a vendor-specified ID. </p>
</dd>

### -field NumberOfPorts

<dd>
<p>Indicates the number of ports on the HBA. </p>
</dd>

### -field DriverName

<dd>
<p>Contains a string not exceeding 256 bytes in length that indicates name of the file that contains the binary image of the device driver for the HBA. </p>
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
<dt>Hbaapi.h (include Hbaapi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\hbaapi\nf-hbaapi-hba-getadapterattributes.md">HBA_GetAdapterAttributes</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_AdapterAttributes structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>