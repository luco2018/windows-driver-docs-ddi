---
UID: NS.dmusprop._SYNTH_BUFFER
title: SYNTH_BUFFER
author: windows-driver-content
description: The SYNTH_BUFFER structure specifies DLS data that is being downloaded to a synthesizer.
old-location: audio\synth_buffer.htm
old-project: audio
ms.assetid: 51b16308-47a8-42e0-9393-fd93045e4e47
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SYNTH_BUFFER, SYNTH_BUFFER, *PSYNTH_BUFFER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dmusprop.h
req.include-header: Dmusprop.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SYNTH_BUFFER
req.alt-loc: dmusprop.h
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
req.iface: ISynthSinkDMus
---

# SYNTH_BUFFER structure



## -description
<p>The SYNTH_BUFFER structure specifies DLS data that is being downloaded to a synthesizer.</p>


## -syntax

````
typedef struct _SYNTH_BUFFER {
  ULONG BufferSize;
  PVOID BufferAddress;
} SYNTH_BUFFER, *PSYNTH_BUFFER;
````


## -struct-fields
<dl>

### -field BufferSize

<dd>
<p>Specifies the size in bytes of the buffer that <b>BufferAddress</b> points to.</p>
</dd>

### -field BufferAddress

<dd>
<p>Pointer to a user-mode address that needs to be converted for kernel use.</p>
</dd>
</dl>

## -remarks
<p>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff537396">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a> set-property request uses the SYNTH_BUFFER structure for its property value.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dmusprop.h (include Dmusprop.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537396">KSPROPERTY_SYNTH_DLS_DOWNLOAD</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20SYNTH_BUFFER structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>