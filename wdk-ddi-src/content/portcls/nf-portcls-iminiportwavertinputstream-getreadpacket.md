---
UID: NF.portcls.IMiniportWaveRTInputStream.GetReadPacket
title: IMiniportWaveRTInputStream::GetReadPacket
author: windows-driver-content
description: Returns information about captured data.
old-location: audio\iminiportwavertinputstream_getreadpacket.htm
old-project: audio
ms.assetid: F26F6820-B761-4DF3-B7D7-9C1B174DEEA2
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IMiniportWaveRTInputStream, GetReadPacket, IMiniportWaveRTInputStream::GetReadPacket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportWaveRTInputStream.GetReadPacket
req.alt-loc: portcls.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Passive level
req.iface: IMiniportWaveRTInputStream
---

# IMiniportWaveRTInputStream::GetReadPacket method



## -description
<p></p>
<p>Returns information about captured data. 
</p>


## -syntax

````
NTSTATUS GetReadPacket(
  [out] ULONG     *PacketNumber,
  [out] DWORD     *Flags,
  [out] ULONGLONG *PerformanceCount,
  [out] BOOL      *MoreData
);
````


## -parameters
<dl>

### -param PacketNumber [out]

<dd>
<p>Returns the packet number relative to the start of capture.  </p>
</dd>

### -param Flags [out]

<dd>
<p>Reserved for future use. Must be set to 0.</p>
</dd>

### -param PerformanceCount [out]

<dd>
<p>Returns the performance counter value corresponding to the sampling instant of the first sample in the packet. 
</p>
</dd>

### -param MoreData [out]

<dd>
<p> Returns <b>TRUE</b> if there is more data ready immediately. The OS may optionally immediately call this routine again after processing the packet to get the next packet information. If the driver returns <b>FALSE</b>, then capture is operating at real time. 
</p>
</dd>
</dl>

## -returns
<p><code>GetReadPacket</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the function returns an appropriate error status code.</p>

<p> STATUS_DEVICE_NOT_READY - The driver returns this error if no new data is available.</p>

## -remarks
<p>Before reading captured audio data from the WaveRT buffer, the OS calls this routine to get information about the available data. 
</p>

<p>The packet number identifies a packet within the stream. This resets to zero when the stream is in KSSTATE_STOP. The number advances with each captured buffer. From the packet number the OS can derive the packet location within the WaveRT buffer and can also derive the stream position of the packet relative to start of stream. 
</p>

<p>The packet size is the WaveRT buffer size divided by the NotificationCount passed to <a href="audio.iminiportwavertstreamnotification_allocatebufferwithnotification">IMiniportWaveRTStreamNotification::AllocateBufferWithNotification</a>. The OS may call this routine at any time. In normal operation, the OS calls this routine after the driver sets the buffer notification event or after a previous call returns true for MoreData. When the OS calls this routine, the driver may assume that the OS has finished reading all previous packets. If the hardware has captured enough data, the driver may immediately burst the next complete packet to the WaveRT buffer and set the buffer event again.In the case of capture overflow (when the OS does not read data quickly enough) the audio driver may drop or overwrite some audio data. The audio driver drops or overwrites oldest data first, The audio driver may continue to advance its internal packet counter even though the OS may not have read the data.  
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 10 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p> Passive level</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\portcls\nn-portcls-iminiportwavertinputstream.md">IMiniportWaveRTInputStream</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWaveRTInputStream::GetReadPacket method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>