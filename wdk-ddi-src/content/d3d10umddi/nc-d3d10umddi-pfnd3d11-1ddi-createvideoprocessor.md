---
UID: NC.d3d10umddi.PFND3D11_1DDI_CREATEVIDEOPROCESSOR
title: PFND3D11_1DDI_CREATEVIDEOPROCESSOR
author: windows-driver-content
description: Creates a video processor object.
old-location: display\createvideoprocessor1.htm
old-project: display
ms.assetid: 741045a2-0a91-490a-907d-5f4900a4a0ae
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateVideoProcessor
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback



## -description
<p>Creates a video processor object.</p>


## -prototype

````
PFND3D11_1DDI_CREATEVIDEOPROCESSOR CreateVideoProcessor;

HRESULT APIENTRY* CreateVideoProcessor(
  _In_       D3D10DDI_HDEVICE                   hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEOPROCESSOR *pCreateData,
  _In_       D3D11_1DDI_HVIDEOPROCESSOR         hVideoProcessor,
  _In_       D3D11_1DDI_HRTVIDEOPROCESSOR       hRTVideoProcessor
)
{ ... }
````


## -parameters
<dl>

### -param hDevice [in]

<dd>
<p>A handle to the display device (graphics context).

</p>
</dd>

### -param pCreateData [in]

<dd>
<p>A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1ddiarg-createvideoprocessor.md">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a> structure. This structure specifies the attributes of the video processor object to be created.</p>
</dd>

### -param hVideoProcessor [in]

<dd>
<p>A handle to the driver's private data for the video processor object. For more information, see the Remarks section.</p>
</dd>

### -param hRTVideoProcessor [in]

<dd>
<p>A handle to the video processor object that the driver should use when it calls back into the Direct3D runtime.</p>
</dd>
</dl>

## -returns
<p><b>CreateVideoProcessor</b> returns one of the following values:</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The video processor object was created successfully.</p><dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl><p>The graphics adapter was removed.</p><dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl><p>
        Memory was not available to complete the operation.</p>

<p> </p>

## -remarks
<p>The <i>CreateVideoProcessor</i> function creates a video processor object that contains specific capabilities and state.  Multiple video processor objects can exist at the same time, each with its own unique state.</p>

<p>The Direct3D runtime calls <i>CreateVideoProcessor</i> after it has called the driver's <a href="display.calcprivatevideoprocessorsize">CalcPrivateVideoProcessorSize</a>   to determine the size in bytes for the private data that the driver requires for the video processor object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video processor object.</p>

<p>When the runtime  calls <i>CreateVideoProcessor</i>, it passes the handle to the private data memory in the <i>hProcessor</i> parameter. This handle is actually a pointer to the memory.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.calcprivatevideoprocessorsize">CalcPrivateVideoProcessorSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11-1ddiarg-createvideoprocessor.md">D3D11_1DDIARG_CREATEVIDEOPROCESSOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEVIDEOPROCESSOR callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>