---
UID: NI.ntdddisk.IOCTL_DISK_GET_CACHE_INFORMATION
title: IOCTL_DISK_GET_CACHE_INFORMATION
author: windows-driver-content
description: Returns disk cache configuration data.
old-location: storage\ioctl_disk_get_cache_information.htm
old-project: storage
ms.assetid: fc651954-2048-4358-91b0-4d99e38e9a67
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: _DETECTION_TYPE, DETECTION_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_DISK_GET_CACHE_INFORMATION
req.alt-loc: Ntdddisk.h
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

# IOCTL_DISK_GET_CACHE_INFORMATION IOCTL



## -description

Returns disk cache configuration data.

Returns disk cache configuration data.


## -ioctlparameters

### -input-buffer
<a id="Input_Buffer"></a><a id="input_buffer"></a><a id="INPUT_BUFFER"></a>Input Buffer
<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be &gt;= <b>sizeof</b>(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL. 
<b>Parameters.DeviceIoControl.OutputBufferLength</b>Parameters.DeviceIoControl.OutputBufferLength in the I/O stack location of the IRP indicates the size, in bytes, of the buffer made available to the driver, which must be >= <b>sizeof</b>sizeof(DISK_CACHE_INFORMATION). Otherwise, the driver returns with an error status of STATUS_BUFFER_TOO_SMALL. 


### -input-buffer-length

<text></text>

### -output-buffer
<a id="Output_Buffer"></a><a id="output_buffer"></a><a id="OUTPUT_BUFFER"></a>Output Buffer
The device driver returns the <a href="storage.disk_cache_information">DISK_CACHE_INFORMATION</a> in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. The device driver returns the <a href="storage.disk_cache_information">DISK_CACHE_INFORMATION</a><b>DISK_CACHE_INFORMATION</b>DISK_CACHE_INFORMATION in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>Irp->AssociatedIrp.SystemBuffer. 


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
<a id="I_O_Status_Block"></a><a id="i_o_status_block"></a><a id="I_O_STATUS_BLOCK"></a>I/O Status Block
The <b>Information</b> field is set to the size of the block of status information being returned, <b>sizeof</b>(DISK_CACHE_INFORMATION). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DEVICE_NOT_READY, STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_NOT_SUPPORTED.The <b>Information</b>Information field is set to the size of the block of status information being returned, <b>sizeof</b>sizeof(DISK_CACHE_INFORMATION). The <b>Status</b>Status field is set to STATUS_SUCCESS, or possibly to STATUS_DEVICE_NOT_READY, STATUS_BUFFER_TOO_SMALL, STATUS_INSUFFICIENT_RESOURCES, STATUS_IO_DEVICE_ERROR, or STATUS_NOT_SUPPORTED.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntdddisk.h (include Ntdddisk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.disk_cache_information">DISK_CACHE_INFORMATION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_DISK_GET_CACHE_INFORMATION control code%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>