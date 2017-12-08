---
UID: NF.portcls.IMiniportWavePci.NewStream
title: IMiniportWavePci::NewStream
author: windows-driver-content
description: The NewStream method creates a new instance of a logical stream associated with a specified physical channel.
old-location: audio\iminiportwavepci_newstream.htm
old-project: audio
ms.assetid: cad3eeb5-2106-4648-97e5-cf3bb8601599
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IMiniportWavePci, NewStream, IMiniportWavePci::NewStream
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IMiniportWavePci.NewStream
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
req.irql: PASSIVE_LEVEL
req.iface: IMiniportWavePci
---

# IMiniportWavePci::NewStream method



## -description
<p>The <code>NewStream</code> method creates a new instance of a logical stream associated with a specified physical channel.</p>


## -syntax

````
NTSTATUS NewStream(
  [out]          PMINIPORTWAVEPCISTREAM *Stream,
  [in, optional] PUNKNOWN               OuterUnknown,
  [in]           POOL_TYPE              PoolType,
  [in]           PPORTWAVEPCISTREAM     PortStream,
  [in]           ULONG                  Pin,
  [in]           BOOLEAN                Capture,
  [in]           PKSDATAFORMAT          DataFormat,
  [out]          PDMACHANNEL            *DmaChannel,
  [out]          PSERVICEGROUP          *ServiceGroup
);
````


## -parameters
<dl>

### -param Stream [out]

<dd>
<p>Output pointer for the new stream. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream object's <a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a> interface. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.</p>
</dd>

### -param OuterUnknown [in, optional]

<dd>
<p>Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the stream object. This parameter is optional. If aggregation is not required, the caller specifies this parameter as <b>NULL</b>.</p>
</dd>

### -param PoolType [in]

<dd>
<p>Specifies the type of memory pool from which the storage for the DMA-channel object should be allocated. This parameter will be one of the nonpaged pool types defined in the <a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a> enumeration.</p>
</dd>

### -param PortStream [in]

<dd>
<p>Pointer to the <a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a> interface of the port driver's stream object.</p>
</dd>

### -param Pin [in]

<dd>
<p>Specifies a pin ID identifying the pin that is to be opened. If the WavePci miniport driver's filter descriptor specifies a total of <i>n</i> pin factories on the filter, then valid values for parameter <i>Pin</i> are in the range 0 to <i>n</i>-1.</p>
</dd>

### -param Capture [in]

<dd>
<p>Specifies whether to create a capture stream or a render stream. This parameter is <b>TRUE</b> for an capture (input) channel, and <b>FALSE</b> for an playback (output) channel.</p>
</dd>

### -param DataFormat [in]

<dd>
<p>Pointer to a <a href="stream.ksdataformat">KSDATAFORMAT</a> structure that specifies the stream's data format.</p>
</dd>

### -param DmaChannel [out]

<dd>
<p>Output pointer for the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the stream's <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> object. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.</p>
</dd>

### -param ServiceGroup [out]

<dd>
<p>Output pointer for the service group. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the <a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a> interface of the stream's service group object. This is the service group that is being registered for interrupt notification. The caller specifies a valid, non-<b>NULL</b> pointer for this parameter.</p>
</dd>
</dl>

## -returns
<p><code>NewStream</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.</p>

## -remarks
<p>The <code>NewStream</code> method sets the initial state of the stream to KSSTATE_STOP and its initial position to zero. (See <a href="audio.iminiportwavepcistream_setstate">IMiniportWavePciStream::SetState</a> and <a href="audio.iminiportwavepcistream_getposition">IMiniportWavePciStream::GetPosition</a>.)</p>

<p>The <i>DataFormat</i> parameter, which specifies the data format of the stream, points to one of the following audio-specific, extended versions of the <a href="stream.ksdataformat">KSDATAFORMAT</a> structure:</p>

<p>
<a href="audio.ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>
</p>

<p>
<a href="audio.ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>
</p>

<p>If the miniport driver does not provide a service group pointer (that is, if the <code>NewStream</code> call outputs <b>NULL</b> through the <i>ServiceGroup</i> pointer), the port driver sets up its own periodic timer instead for processing stream position and clock events. The period for this timer is currently 20 milliseconds, but the period might change in future implementations.</p>

<p>The <i>Stream</i>, <i>OuterUnknown</i>, <i>PortStream</i>, and <i>ServiceGroup</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.</p>

<p>Note that <code>NewStream</code> does not follow the usual reference-counting conventions in its handling of the pointer that it outputs through the <i>DmaChannel</i> OUT parameter. When the port driver finishes using the references that it receives through the <code>NewStream</code> method's other OUT parameters, <i>Stream</i> and <i>ServiceGroup</i>, it releases them, as expected. In contrast, the port driver never uses the <i>DmaChannel</i> pointer that it receives from the <code>NewStream</code> call and it never calls <b>Release</b> on the <i>DmaChannel</i> object.</p>

<p>The ac97 sample audio driver in the Microsoft Windows Driver Kit (WDK) reflects this behavior. This sample's implementation of the <code>IMiniportWavePci::NewStream</code> method calls <b>AddRef</b> on the <i>Stream</i> and <i>ServiceGroup</i> references that it outputs but not the <i>DmaChannel</i> reference. This behavior is preserved for the sake of backward compatibility.</p>

<p>Note that the <code>NewStream</code> methods for the other port types (WaveCyclic, in particular) follow the usual reference-counting conventions for all their OUT parameters. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
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
<a href="..\portcls\nn-portcls-iminiportwavepci.md">IMiniportWavePci</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iminiportwavepcistream.md">IMiniportWavePciStream</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iportwavepcistream.md">IPortWavePciStream</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iservicegroup.md">IServiceGroup</a>
</dt>
<dt>
<a href="stream.ksdataformat">KSDATAFORMAT</a>
</dt>
<dt>
<a href="audio.ksdataformat_dsound">KSDATAFORMAT_DSOUND</a>
</dt>
<dt>
<a href="audio.ksdataformat_waveformatex">KSDATAFORMAT_WAVEFORMATEX</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IMiniportWavePci::NewStream method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>