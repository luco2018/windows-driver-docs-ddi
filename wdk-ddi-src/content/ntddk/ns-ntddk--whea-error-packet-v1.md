---
UID: NS.ntddk._WHEA_ERROR_PACKET_V1
title: WHEA_ERROR_PACKET_V1
author: windows-driver-content
description: The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).Note  The WHEA_ERROR_PACKET_V1 structure is supported in Windows Server 2008 and Windows Vista SP1.
old-location: whea\whea_error_packet_v1.htm
old-project: whea
ms.assetid: 66189a9a-241f-4457-87cd-d5d583a46f14
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_ERROR_PACKET_V1, WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET_V1
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
req.alt-api: WHEA_ERROR_PACKET_V1
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

# WHEA_ERROR_PACKET_V1 structure



## -description
<p>The WHEA_ERROR_PACKET_V1 structure describes the hardware error data that is passed to the operating system by a low-level hardware error handler (LLHEH).</p>


## -syntax

````
typedef struct _WHEA_ERROR_PACKET_V1 {
  ULONG                   Signature;
  WHEA_ERROR_PACKET_FLAGS Flags;
  ULONG                   Size;
  ULONG                   RawDataLength;
  ULONGLONG               Reserved1;
  ULONGLONG               Context;
  WHEA_ERROR_TYPE         ErrorType;
  WHEA_ERROR_SEVERITY     ErrorSeverity;
  ULONG                   ErrorSourceId;
  WHEA_ERROR_SOURCE_TYPE  ErrorSourceType;
  ULONG                   Reserved2;
  ULONG                   Version;
  ULONGLONG               Cpu;
  union {
    WHEA_PROCESSOR_GENERIC_ERROR_SECTION ProcessorError;
    WHEA_MEMORY_ERROR_SECTION            MemoryError;
    WHEA_NMI_ERROR_SECTION               NmiError;
    WHEA_PCIEXPRESS_ERROR_SECTION        PciExpressError;
    WHEA_PCIXBUS_ERROR_SECTION           PciXBusError;
    WHEA_PCIXDEVICE_ERROR_SECTION        PciXDeviceError;
  } u;
  WHEA_RAW_DATA_FORMAT    RawDataFormat;
  ULONG                   RawDataOffset;
  UCHAR                   RawData[1];
} WHEA_ERROR_PACKET_V1, *PWHEA_ERROR_PACKET_V1;
````


## -struct-fields
<dl>

### -field Signature

<dd>
<p>The signature of the hardware error packet. This member contains the value WHEA_ERROR_PACKET_V1_SIGNATURE.</p>
</dd>

### -field Flags

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-error-packet-flags.md">WHEA_ERROR_PACKET_FLAGS</a> union that describes the error condition. </p>
</dd>

### -field Size

<dd>
<p>The size, in bytes, of the hardware error packet, including the raw data.</p>
</dd>

### -field RawDataLength

<dd>
<p>The length, in bytes, of the data that is contained in the <b>RawData</b> member.</p>
</dd>

### -field Reserved1

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Context

<dd>
<p>Reserved for system use.</p>
</dd>

### -field ErrorType

<dd>
<p>A <a href="..\ntddk\ne-ntddk--whea-error-type.md">WHEA_ERROR_TYPE</a>-typed value that indicates the type of hardware component that reported the hardware error.</p>
</dd>

### -field ErrorSeverity

<dd>
<p>A <a href="..\ntddk\ne-ntddk--whea-error-severity.md">WHEA_ERROR_SEVERITY</a>-typed value that indicates the severity of the error condition.</p>
</dd>

### -field ErrorSourceId

<dd>
<p>The identifier of the error source that reported the hardware error.</p>
</dd>

### -field ErrorSourceType

<dd>
<p>A <a href="..\ntddk\ne-ntddk--whea-error-source-type.md">WHEA_ERROR_SOURCE_TYPE</a>-typed value that indicates the type of error source that reported the hardware error.</p>
</dd>

### -field Reserved2

<dd>
<p>Reserved for system use.</p>
</dd>

### -field Version

<dd>
<p>The version of the WHEA_ERROR_PACKET_V1 structure. This member contains the value WHEA_ERROR_PKT_V1VERSION.</p>
</dd>

### -field Cpu

<dd>
<p>Reserved for system use.</p>
</dd>

### -field u

<dd>
<p>A union consisting of the following members:</p>
<dl>

### -field ProcessorError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-processor-generic-error-section.md">WHEA_PROCESSOR_GENERIC_ERROR_SECTION</a> structure that describes processor error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeProcessor</b>. </p>
</dd>

### -field MemoryError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-memory-error-section.md">WHEA_MEMORY_ERROR_SECTION</a> structure that describes memory error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeMemory</b>. </p>
</dd>

### -field NmiError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-nmi-error-section.md">WHEA_NMI_ERROR_SECTION</a> structure that describes nonmaskable interrupt (NMI) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypeNMI</b>. </p>
</dd>

### -field PciExpressError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-pciexpress-error-section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure that describes PCI Express (PCIe) error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIExpress</b>. </p>
</dd>

### -field PciXBusError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-pcixbus-error-section.md">WHEA_PCIXBUS_ERROR_SECTION</a> structure that describes PCI or PCI-X bus error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXBus</b>. </p>
</dd>

### -field PciXDeviceError

<dd>
<p>A <a href="..\ntddk\ns-ntddk--whea-pcixdevice-error-section.md">WHEA_PCIXDEVICE_ERROR_SECTION</a> structure that describes PCI or PCI-X device error data. This member is used only when the <b>ErrorType</b> member is set to <b>WheaErrTypePCIXDevice</b>. </p>
</dd>
</dl>
</dd>

### -field RawDataFormat

<dd>
<p>A <a href="..\ntddk\ne-ntddk--whea-raw-data-format.md">WHEA_RAW_DATA_FORMAT</a>-typed value that indicates the format of the hardware error information that is contained in the <b>RawData</b> data buffer.</p>
</dd>

### -field RawDataOffset

<dd>
<p>An offset, in bytes, from the beginning of the <b>RawData</b> data buffer where a PSHED plug-in can add supplementary platform-specific error information to the hardware error packet. The amount of supplementary information that can be added to the hardware error packet is limited by the total size of the packet as specified in the <b>Size</b> member.</p>
</dd>

### -field RawData

<dd>
<p>A variable-sized data buffer that contains the raw hardware error information from the error source's status registers. The format of the hardware error data is specified by the <b>RawDataFormat</b> member.</p>
</dd>
</dl>

## -remarks
<p>The WHEA_ERROR_PACKET_V1 structure is used to report a hardware error in Windows Server 2008 and Windows Vista SP1.</p>

<p>If your <a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">platform-specific hardware error driver (PSHED) plug-ins</a> run on any WHEA-compatible Windows version, You can inspect the version of WHEA_ERROR_PACKET by following these steps:</p>

<p>If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V1, the code is running on an early version of Windows, and the error packet is formatted as a <b>WHEA_ERROR_PACKET_V1</b> structure.</p>

<p>If the <b>Signature</b> member for the WHEA_ERROR_PACKET equals WHEA_ERROR_PACKET_V2, the code is running on a later version of Windows, and the error packet is formatted as a <a href="..\ntddk\ns-ntddk--whea-error-packet-v2.md">WHEA_ERROR_PACKET_V2</a> structure.</p>

<p>An LLHEH passes a WHEA_ERROR_PACKET_V1 structure to the operating system when it reports a hardware error. This hardware error packet contains the raw hardware error data direct from the error source's error status registers.</p>

<p>The WHEA_ERROR_PACKET_V1 structure describes the error data that is contained in a hardware error packet error section of an <a href="https://msdn.microsoft.com/080da29a-b5cb-45a5-848d-048d9612ee2a">error record</a>. An error record contains a hardware error packet error section only if the  <b>SectionType</b> member of one of the <a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures that describe the error record sections for that error record contains WHEA_PACKET_SECTION_GUID.</p>

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
<a href="https://msdn.microsoft.com/473d9206-9db2-4bc7-bc76-6be2fb77b20b">Platform-Specific Hardware Error Driver (PSHED) Plug-Ins</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-packet-flags.md">WHEA_ERROR_PACKET_FLAGS</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-packet-v2.md">WHEA_ERROR_PACKET_V2</a>
</dt>
<dt>
<a href="..\ntddk\ns-ntddk--whea-error-record-section-descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk--whea-error-severity.md">WHEA_ERROR_SEVERITY</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk--whea-error-source-type.md">WHEA_ERROR_SOURCE_TYPE</a>
</dt>
<dt>
<a href="..\ntddk\ne-ntddk--whea-error-type.md">WHEA_ERROR_TYPE</a>
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
<a href="..\ntddk\ne-ntddk--whea-raw-data-format.md">WHEA_RAW_DATA_FORMAT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_PACKET_V1 structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>