---
UID: NS.ntddk._WHEA_XPF_TLB_CHECK
title: WHEA_XPF_TLB_CHECK
author: windows-driver-content
description: The WHEA_XPF_TLB_CHECK union describes translation lookaside buffer (TLB) error information for an x86 or x64 processor.
old-location: whea\whea_xpf_tlb_check.htm
old-project: whea
ms.assetid: 3943c854-3bb9-4fc9-9af9-735c3f4ee94e
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WHEA_XPF_TLB_CHECK, WHEA_XPF_TLB_CHECK, *PWHEA_XPF_TLB_CHECK
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
req.alt-api: WHEA_XPF_TLB_CHECK
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

# WHEA_XPF_TLB_CHECK structure



## -description
<p>The WHEA_XPF_TLB_CHECK union describes translation lookaside buffer (TLB) error information for an x86 or x64 processor.</p>


## -syntax

````
typedef union _WHEA_XPF_TLB_CHECK {
  struct {
    ULONGLONG TransactionTypeValid  :1;
    ULONGLONG OperationValid  :1;
    ULONGLONG LevelValid  :1;
    ULONGLONG ProcessorContextCorruptValid  :1;
    ULONGLONG UncorrectedValid  :1;
    ULONGLONG PreciseIPValid  :1;
    ULONGLONG RestartableIPValid  :1;
    ULONGLONG OverflowValid  :1;
    ULONGLONG ReservedValid  :8;
    ULONGLONG TransactionType  :2;
    ULONGLONG Operation  :4;
    ULONGLONG Level  :3;
    ULONGLONG ProcessorContextCorrupt  :1;
    ULONGLONG Uncorrected  :1;
    ULONGLONG PreciseIP  :1;
    ULONGLONG RestartableIP  :1;
    ULONGLONG Overflow  :1;
    ULONGLONG Reserved  :34;
  };
  ULONGLONG XpfTLBCheck;
} WHEA_XPF_TLB_CHECK, *PWHEA_XPF_TLB_CHECK;
````


## -struct-fields
<dl>

### -field TransactionTypeValid

<dd>
<p>A single bit that indicates that the <b>TransactionType</b> member contains valid data.</p>
</dd>

### -field OperationValid

<dd>
<p>A single bit that indicates that the <b>Operation</b> member contains valid data.</p>
</dd>

### -field LevelValid

<dd>
<p>A single bit that indicates that the <b>Level</b> member contains valid data.</p>
</dd>

### -field ProcessorContextCorruptValid

<dd>
<p>A single bit that indicates that the <b>ProcessorContextCorrupt</b> member contains valid data.</p>
</dd>

### -field UncorrectedValid

<dd>
<p>A single bit that indicates that the <b>Uncorrected</b> member contains valid data.</p>
</dd>

### -field PreciseIPValid

<dd>
<p>A single bit that indicates that the <b>PreciseIP</b> member contains valid data.</p>
</dd>

### -field RestartableIPValid

<dd>
<p>A single bit that indicates that the <b>RestartableIP</b> member contains valid data.</p>
</dd>

### -field OverflowValid

<dd>
<p>A single bit that indicates that the <b>Overflow</b> member contains valid data.</p>
</dd>

### -field ReservedValid

<dd>
<p>Reserved for system use.</p>
</dd>

### -field TransactionType

<dd>
<p>The type of transaction that was in progress when the error occurred. Possible values are:</p>
<p></p>
<dl>

### -field XPF_TLB_CHECK_TRANSACTIONTYPE_INSTRUCTION

<dd>
<p>A processor instruction transaction.</p>
</dd>

### -field XPF_TLB_CHECK_TRANSACTIONTYPE_DATAACCESS

<dd>
<p>A data access transaction.</p>
</dd>

### -field XPF_TLB_CHECK_TRANSACTIONTYPE_GENERIC

<dd>
<p>A generic transaction.</p>
</dd>
</dl>
<p>This member contains valid data only if the <b>TransactionTypeValid</b> bit is set.</p>
</dd>

### -field Operation

<dd>
<p>The type of translation lookaside buffer (TLB) access operation that caused the error. Possible values are:</p>
<p></p>
<dl>

### -field XPF_TLB_CHECK_OPERATION_GENERIC

<dd>
<p>The type of operation cannot be determined.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_GENREAD

<dd>
<p>A generic read operation.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_GENWRITE

<dd>
<p>A generic write operation.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_DATAREAD

<dd>
<p>A data read operation.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_DATAWRITE

<dd>
<p>A data write operation.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_INSTRUCTIONFETCH

<dd>
<p>An instruction fetch operation.</p>
</dd>

### -field XPF_TLB_CHECK_OPERATION_PREFETCH

<dd>
<p>An instruction prefetch operation.</p>
</dd>
</dl>
<p>This member contains valid data only if the <b>OperationValid</b> bit is set.</p>
</dd>

### -field Level

<dd>
<p>The level of the TLB where the error occurred.</p>
<p>This member contains valid data only if the <b>LevelValid</b> bit is set.</p>
</dd>

### -field ProcessorContextCorrupt

<dd>
<p>A single bit that indicates that the processor context might have been corrupted.</p>
<p>This member contains valid data only if the <b>ProcessorContextCorruptValid</b> bit is set.</p>
</dd>

### -field Uncorrected

<dd>
<p>A single bit that indicates that the error has not been corrected.</p>
<p>This member contains valid data only if the <b>UncorrectedValid</b> bit is set.</p>
</dd>

### -field PreciseIP

<dd>
<p>A single bit that indicates that the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk--whea-xpf-procinfo.md">WHEA_XPF_PROCINFO</a> structure that contains this WHEA_XPF_TLB_CHECK union is directly associated with the error.</p>
<p>This member contains valid data only if the <b>PreciseIPValid</b> bit is set.</p>
</dd>

### -field RestartableIP

<dd>
<p>A single bit that indicates that program execution can be restarted reliably at the instruction pointer that is specified in the <b>InstructionPointer</b> member of the <a href="..\ntddk\ns-ntddk--whea-xpf-procinfo.md">WHEA_XPF_PROCINFO</a> union that contains this WHEA_XPF_TLB_CHECK structure.</p>
<p>This member contains valid data only if the <b>RestartableIPValid</b> bit is set.</p>
</dd>

### -field Overflow

<dd>
<p>A single bit that indicates that an error overflow occurred.</p>
<p>This member contains valid data only if the <b>OverflowValid</b> bit is set.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved for system use.</p>
</dd>

### -field XpfTLBCheck

<dd>
<p>A ULONGLONG representation of the contents of the WHEA_XPF_TLB_CHECK union.</p>
</dd>
</dl>

## -remarks
<p>If the <b>CheckInfoId</b> member of a <a href="..\ntddk\ns-ntddk--whea-xpf-procinfo.md">WHEA_XPF_PROCINFO</a> structure contains WHEA_TLBCHECK_GUID, the <b>CheckInfo</b> member of the WHEA_XPF_PROCINFO structure contains a WHEA_XPF_TLB_CHECK union.</p>

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
<a href="..\ntddk\ns-ntddk--whea-xpf-procinfo.md">WHEA_XPF_PROCINFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_XPF_TLB_CHECK union%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>