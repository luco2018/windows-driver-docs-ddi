---
UID: NI.bthhfpddi.IOCTL_BTHHFP_STREAM_CLOSE
title: IOCTL_BTHHFP_STREAM_CLOSE
author: windows-driver-content
description: The IOCTL_BTHHFP_STREAM_CLOSE IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.
old-location: audio\ioctl_bthhfp_stream_close.htm
old-project: audio
ms.assetid: 689296FA-E28A-4F9C-8E09-2CAC8A189808
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: BTHHFP_AUDIO_DEVICE_CAPABILTIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthhfpddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_BTHHFP_STREAM_CLOSE
req.alt-loc: Bthhfpddi.h
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

# IOCTL_BTHHFP_STREAM_CLOSE IOCTL



## -description
<p>The <b>IOCTL_BTHHFP_STREAM_CLOSE</b> 
   IOCTL indicates that the client driver no longer requires the synchronous connection-oriented (SCO) channel for streaming audio.</p>


## -ioctlparameters

### -input-buffer
<p>N/A</p>

### -input-buffer-length
<p>N/A</p>

<p>N/A</p>

### -output-buffer
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

### -output-buffer-length
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

<p>N/A</p>

## -remarks
<p>The request completes immediately.</p>

<p>The audio driver starts this request when the KS pin transitions to the KSSTATE_STOP state, and should not finish the pin state transition until this request completes.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bthhfpddi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.bluetooth_hfp_ddi_ioctls">Bluetooth HFP DDI IOCTLs</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IOCTL_BTHHFP_STREAM_CLOSE control code%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>