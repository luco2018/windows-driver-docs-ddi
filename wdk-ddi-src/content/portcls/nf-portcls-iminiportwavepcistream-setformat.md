---
UID: NF:portcls.IMiniportWavePciStream.SetFormat
title: IMiniportWavePciStream::SetFormat
author: windows-driver-content
description: The SetFormat method sets the KS data format of the wave stream.
old-location: audio\iminiportwavepcistream_setformat.htm
old-project: audio
ms.assetid: c8dfa58d-f38b-4ef1-9607-575191d8ddea
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IMiniportWavePciStream interface [Audio Devices],SetFormat method, IMiniportWavePciStream.SetFormat, IMiniportWavePciStream::SetFormat, SetFormat, SetFormat method [Audio Devices], SetFormat method [Audio Devices],IMiniportWavePciStream interface, audio.iminiportwavepcistream_setformat, audmp-routines_7b5ce806-912e-4c30-9f3e-4a2b31a12864.xml, portcls/IMiniportWavePciStream::SetFormat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IMiniportWavePciStream.SetFormat
product:
- Windows
targetos: Windows
req.typenames: 
---

# IMiniportWavePciStream::SetFormat


## -description


The <code>SetFormat</code> method sets the KS data format of the wave stream.


## -parameters




### -param DataFormat [in]

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a> structure that describes the new format of the stream.


## -returns



<code>SetFormat</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



The wave stream's initial format is specified in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a> call that creates the stream. Following stream creation, the <code>SetFormat</code> call can change the stream's format from its initial setting.

For information about specifying wave stream formats, see <a href="https://msdn.microsoft.com/85aa74b4-8e33-49f4-82e7-561baa55c265">Audio Data Formats and Data Ranges</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536735">IMiniportWavePci::NewStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536725">IMiniportWavePciStream</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>
 

 

