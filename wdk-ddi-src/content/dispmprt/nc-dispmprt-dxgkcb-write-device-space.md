---
UID: NC.dispmprt.DXGKCB_WRITE_DEVICE_SPACE
title: DXGKCB_WRITE_DEVICE_SPACE
author: windows-driver-content
description: The DxgkCbWriteDeviceSpace function writes to a device configuration space or the expansion ROM of a display adapter.
old-location: display\dxgkcbwritedevicespace.htm
old-project: display
ms.assetid: 797d6b0c-91a4-4923-ad40-937cfde50067
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SYMBOL_INFO_EX, SYMBOL_INFO_EX, *PSYMBOL_INFO_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbWriteDeviceSpace
req.alt-loc: dispmprt.h
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
req.iface: IDebugSystemObjects4
---

# DXGKCB_WRITE_DEVICE_SPACE callback



## -description
<p>The <b>DxgkCbWriteDeviceSpace</b> function writes to a device configuration space or the expansion ROM of a display adapter.</p>


## -prototype

````
DXGKCB_WRITE_DEVICE_SPACE DxgkCbWriteDeviceSpace;

NTSTATUS DxgkCbWriteDeviceSpace(
  _In_  HANDLE DeviceHandle,
  _In_  ULONG  DataType,
  _In_  PVOID  Buffer,
  _In_  ULONG  Offset,
  _In_  ULONG  Length,
  _Out_ PULONG BytesWritten
)
{ ... }
````


## -parameters
<dl>

### -param DeviceHandle [in]

<dd>
<p>A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="display.dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to <a href="display.dxgkddistartdevice">DxgkDdiStartDevice</a>.</p>
</dd>

### -param DataType [in]

<dd>
<p>The type of write transaction to be performed. This parameter must be one of the following values, which are defined in <i>Dispmprt.h</i>:</p>
<p></p>
<dl>

### -param DXGK_WHICHSPACE_BRIDGE

<dd>
<p>Write to the parent bus device's configuration space.</p>
</dd>

### -param DXGK_WHICHSPACE_CONFIG

<dd>
<p>Write to the display adapter's configuration space.</p>
</dd>

### -param DXGK_WHICHSPACE_MCH

<dd>
<p>Write to the configuration space of a memory controller hub that is a peer to the adapter's parent bus.</p>
</dd>

### -param DXGK_WHICHSPACE_ROM

<dd>
<p>Write to the display adapter's expansion ROM.</p>
</dd>
</dl>
</dd>

### -param Buffer [in]

<dd>
<p>A pointer to a buffer that supplies the data to be written to the configuration space.</p>
</dd>

### -param Offset [in]

<dd>
<p>The offset, in bytes, into the configuration space, at which the write transaction begins.</p>
</dd>

### -param Length [in]

<dd>
<p>The number of bytes to be written.</p>
</dd>

### -param BytesWritten [out]

<dd>
<p>A pointer to a ULONG-typed variable that receives the number of bytes actually written.</p>
</dd>
</dl>

## -returns
<p><b>DxgkCbWriteDeviceSpace</b> returns one of the following values:</p><dl>
<dt><b>  STATUS_SUCCESS</b></dt>
</dl><p>  The function succeeded.</p><dl>
<dt><b>  STATUS_INVALID_PARAMETER</b></dt>
</dl><p>  The <i>DeviceHandle</i>, <i>DataType</i>, or <i>Buffer</i> parameter is invalid.</p><dl>
<dt><b>  STATUS_UNSUCCESSFUL</b></dt>
</dl><p>  The function was unable to write the data.</p>

<p> </p>

<p>The following code example writes a value of a specific size to the PCI configuration space.</p>

## -remarks


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
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkcb-read-device-space.md">DxgkCbReadDeviceSpace</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_WRITE_DEVICE_SPACE callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>