---
UID: NS:dxva._DXVA_TCoefSingle
title: "_DXVA_TCoefSingle"
author: windows-driver-content
description: The DXVA_TCoefSingle structure is sent by the host decoder to the accelerator to specify IDCT coefficient values.
old-location: display\dxva_tcoefsingle.htm
old-project: display
ms.assetid: 665a9819-d319-414d-9a31-ee565b293197
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPDXVA_TCoefSingle, DXVA_TCoefSingle, DXVA_TCoefSingle structure [Display Devices], LPDXVA_TCoefSingle, LPDXVA_TCoefSingle structure pointer [Display Devices], _DXVA_TCoefSingle, display.dxva_tcoefsingle, dxva/DXVA_TCoefSingle, dxva/LPDXVA_TCoefSingle, dxvaref_2b92ced3-3856-466f-b95a-84dd78426a0e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_TCoefSingle
product:
- Windows
targetos: Windows
req.typenames: DXVA_TCoefSingle, *LPDXVA_TCoefSingle
---

# _DXVA_TCoefSingle structure


## -description


The DXVA_TCoefSingle structure is sent by the host decoder to the accelerator to specify <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">IDCT</a> coefficient values.


## -struct-fields




### -field wIndexWithEOB

This member contains two fields: <i>TCoefIDX </i>and <i>TCoefEOB</i>.





#### TCoefIDX

Specifies the scan index of the coefficient in the block, as determined from the <b>bConfigHostInverseScan</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> structure. This field is in the 15 most significant bits of the <b>wIndexWithEOB </b>member.

There are two ways that <i>TCoefIDX</i> can be used:

<ol>
<li>
Run-length ordering: When <b>bConfigHostInverseScan</b> is zero, the <i>MBscanMethod</i> element of the macroblock control command indicates a zigzag, alternate-vertical, or alternate-horizontal inverse scan. These macroblock control commands are defined in the following structures: <a href="https://msdn.microsoft.com/library/windows/hardware/ff563989">DXVA_MBctrl_I_OffHostIDCT_1</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563997">DXVA_MBctrl_P_OffHostIDCT_1</a>. In this case, <i>TCoefIDX</i> contains the number of zero-valued coefficients that precede the current coefficient in the specified scan order, subsequent to the last transmitted coefficient for the block (or relative to the start of the block if none precede it). Any remaining coefficients after the last sent coefficient in the inverse-scan order are implied to have the value zero.

</li>
<li>
Arbitrary ordering: When <b>bConfigHostInverseScan</b> is 1, the <i>MBscanMethod</i> element of the macroblock control command indicates arbitrary ordering. These macroblock control commands are defined in the following structures: <a href="https://msdn.microsoft.com/library/windows/hardware/ff563989">DXVA_MBctrl_I_OffHostIDCT_1</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff563997">DXVA_MBctrl_P_OffHostIDCT_1</a>. In this case, <i>TCoefIDX</i> simply contains the raster index of the coefficient within the block (TCoefIDX = u + 8 * v, where u and v are the transform-domain horizontal and vertical frequency coordinates), and any coefficients that are not sent are implied to have the value 0.

</li>
</ol>
<i>TCoefIDX</i> must always be less than 64.



#### TCoefEOB

Indicates whether the current coefficient is the last one associated with the current block of transform coefficients. A value of 1 indicates that the current coefficient is the last one for the block and a value of zero indicates that it is not. This field is in the least significant bit of the <b>wIndexWithEOB</b> member. 


### -field TCoefValue

Indicates the value of the coefficient in the block. <b>TCoefValue</b> must be clipped to the appropriate range as specified in <a href="https://msdn.microsoft.com/7736a226-1122-4380-b09f-a8560c0cd609">Low-Level IDCT Processing Elements</a> by the host prior to passing the coefficient value to the accelerator for <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">IDCT</a> operation. MPEG-2 mismatch control, if necessary, is also the responsibility of the host, not the accelerator. (This might require the creation of extra "phantom" nonzero coefficients.)


## -remarks



The DXVA_TCoefSingle structure is used whenever the <i>HostResidDiff</i> flag (bit 10 in the <b>wMBtype</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563997">DXVA_MBctrl_P_OffHostIDCT_1</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff563989">DXVA_MBctrl_I_OffHostIDCT_1</a> structure) is 1 and the <b>bConfig4GroupedCoefs</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a> structure is zero.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563133">DXVA_ConfigPictureDecode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563989">DXVA_MBctrl_I_OffHostIDCT_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563997">DXVA_MBctrl_P_OffHostIDCT_1</a>
 

 

