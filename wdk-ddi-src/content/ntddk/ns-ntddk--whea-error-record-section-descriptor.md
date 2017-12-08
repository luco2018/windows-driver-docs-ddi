---
UID: NS.ntddk._WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
title: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
author: windows-driver-content
description: The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an error record.
old-location: whea\whea_error_record_section_descriptor.htm
old-project: whea
ms.assetid: f1abbf2b-19c9-4d34-9975-4f7ab98792af
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR
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
req.alt-api: WHEA_ERROR_RECORD_SECTION_DESCRIPTOR
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

# WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure



## -description
<p>The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure describes a section of error information that is part of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>.</p>


## -syntax

````
typedef struct _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR {
  ULONG                                          SectionOffset;
  ULONG                                          SectionLength;
  WHEA_REVISION                                  Revision;
  WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS ValidBits;
  UCHAR                                          Reserved;
  WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS     Flags;
  GUID                                           SectionType;
  GUID                                           FRUId;
  WHEA_ERROR_SEVERITY                            SectionSeverity;
  CCHAR                                          FRUText[20];
} WHEA_ERROR_RECORD_SECTION_DESCRIPTOR, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field SectionOffset

<dd>
<p>The offset, in bytes, from the beginning of the error record to the beginning of the error record section.</p>
</dd>

### -field SectionLength

<dd>
<p>The length, in bytes, of the error data contained in the error record section.</p>
</dd>

### -field Revision

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-revision.md">WHEA_REVISION</a> union that describes the revision level of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure.</p>
</dd>

### -field ValidBits

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor-validbits.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a> union that specifies which members of this structure contain valid data.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Flags

<dd>
<p>A WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union that describes the error record section. The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union is defined as follows:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef union _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS {
  struct {
    ULONG  Primary:1;
    ULONG  ContainmentWarning:1;
    ULONG  Reset:1;
    ULONG  ThresholdExceeded:1;
    ULONG  ResourceNotAvailable:1;
    ULONG  LatentError:1;
    ULONG  Reserved:26;
  };
  ULONG  AsULONG;
} WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS;</pre>
</td>
</tr>
</table></span></div>
<p></p>
<dl>

### -field Primary

<dd>
<p>A single bit that indicates that the corresponding error record section is the primary section within the error record. When there are multiple sections contained in an error record, the primary section is the section that is used for error recovery.</p>
</dd>

### -field ContainmentWarning

<dd>
<p>A single bit that indicates that the error described by the corresponding error record section was not contained within the processor or memory hierarchy. In this situation, the error might have propagated to other components of the system.</p>
</dd>

### -field Reset

<dd>
<p>A single bit that indicates that the component must be reinitialized or re-enabled by the operating system.</p>
</dd>

### -field ThresholdExceeded

<dd>
<p>A single bit that indicates that an error threshold has been exceeded.</p>
</dd>

### -field ResourceNotAvailable

<dd>
<p>A single bit that indicates that a resource could not be queried for error information due to conflicts with other system software or resources. In this situation, some of the fields of the corresponding error record section will be invalid.</p>
</dd>

### -field LatentError

<dd>
<p>A single bit that indicates that the reported error is a latent error (one not yet consumed) that could result in a more severe error when it is consumed.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field AsULONG

<dd>
<p>A ULONG representation of the contents of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_FLAGS union.</p>
</dd>
</dl>
</dd>

### -field SectionType

<dd>
<p>A GUID that identifies the type of error data that is contained in the error record section. The standard section types are defined as follows:</p>
<p></p>
<dl>

### -field WHEA_PACKET_SECTION_GUID

<dd>
<p>The error record section contains the hardware error packet that was passed to the operating system by the low-level hardware error handler (LLHEH) that reported the error. This data is described by a <a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a> structure.</p>
</dd>

### -field PROCESSOR_GENERIC_ERROR_SECTION_GUID

<dd>
<p>The error record section contains processor error data that is not specific to a particular processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure.</p>
</dd>

### -field IPF_PROCESSOR_ERROR_SECTION_GUID

<dd>
<p>The error record section contains processor error data that is specific to the Itanium processor architecture. For more information about the format of the error data that is contained in this error record section, see the <a href="http://go.microsoft.com/fwlink/p/?linkid=72212">Intel Itanium Processor Family System Abstraction Layer Specification</a>.</p>
</dd>

### -field FIRMWARE_ERROR_RECORD_REFERENCE_GUID

<dd>
<p>The error record section contains a reference to a firmware error record that is specific to the Itanium processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk--whea-firmware-error-record-reference.md">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a> structure.</p>
</dd>

### -field MEMORY_ERROR_SECTION_GUID

<dd>
<p>The error record section contains platform memory error data. This data is described by a <a href="..\ntddk\ns-ntddk--whea-memory-error-section.md">WHEA_MEMORY_ERROR_SECTION</a> structure.</p>
</dd>

### -field NMI_SECTION_GUID

<dd>
<p>The error record section contains nonmaskable interrupt (NMI) error data. This data is described by a <a href="..\ntddk\ns-ntddk--whea-nmi-error-section.md">WHEA_NMI_ERROR_SECTION</a> structure.</p>
</dd>

### -field PCIEXPRESS_ERROR_SECTION_GUID

<dd>
<p>The error record section contains PCI Express (PCIe) error data. This data is described by a <a href="..\ntddk\ns-ntddk--whea-pciexpress-error-section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.</p>
</dd>

### -field PCIXBUS_ERROR_SECTION_GUID

<dd>
<p>The error record section contains PCI/PCI-X bus error data. This data is described by a <a href="..\ntddk\ns-ntddk--whea-pcixbus-error-section.md">WHEA_PCIXBUS_ERROR_SECTION</a> structure.</p>
</dd>

### -field PCIXBUS_ERROR_SECTION_GUID

<dd>
<p>The error record section contains PCI/PCI-X device error data. This data is described by a <a href="..\ntddk\ns-ntddk--whea-pcixdevice-error-section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure.</p>
</dd>

### -field XPF_PROCESSOR_ERROR_SECTION_GUID

<dd>
<p>The error record section contains processor error data that is specific to the x86 or x64 processor architecture. This data is described by a <a href="..\ntddk\ns-ntddk--whea-xpf-processor-error-section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a> structure.</p>
</dd>
</dl>
<p>For error record sections that do not conform to one of the standard section types, this member contains a platform-specific GUID that identifies the type of error data that is contained in the error record section. If a platform-specific GUID is not defined for the type of error data that is contained in the error record section, this member contains GENERIC_SECTION_GUID.</p>
</dd>

### -field FRUId

<dd>
<p>A GUID that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUId</b> bit is set.</p>
</dd>

### -field SectionSeverity

<dd>
<p>A <a href="..\ntddk\ne-ntddk--whea-error-severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition that is described by the error record section.</p>
</dd>

### -field FRUText

<dd>
<p>A character string that identifies the Field Replaceable Unit (FRU) that contains the hardware where the error occurred. This member contains valid data only if the <b>ValidBits.FRUText</b> bit is set.</p>
</dd>
</dl>

## -remarks
<p>The <a href="..\ntddk\ns-ntddk--whea-error-record.md">WHEA_ERROR_RECORD</a> structure contains an array of WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structures. Each descriptor describes a section of error information that is part of the error record.</p>

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
<a href="whea.whea_error_packet">WHEA_ERROR_PACKET</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-record.md">WHEA_ERROR_RECORD</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor-validbits.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk--whea-error-severity.md">WHEA_ERROR_SEVERITY</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-firmware-error-record-reference.md">WHEA_FIRMWARE_ERROR_RECORD_REFERENCE</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-memory-error-section.md">WHEA_MEMORY_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-nmi-error-section.md">WHEA_NMI_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pciexpress-error-section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pcixbus-error-section.md">WHEA_PCIXBUS_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-pcixdevice-error-section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-revision.md">WHEA_REVISION</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-xpf-processor-error-section.md">WHEA_XPF_PROCESSOR_ERROR_SECTION</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>