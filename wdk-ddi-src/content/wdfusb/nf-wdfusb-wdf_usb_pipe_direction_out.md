---
UID: NF.wdfusb.WDF_USB_PIPE_DIRECTION_OUT
title: WDF_USB_PIPE_DIRECTION_OUT function
author: windows-driver-content
description: The WDF_USB_PIPE_DIRECTION_OUT function determines whether a specified USB endpoint is an output endpoint.
old-location: wdf\wdf_usb_pipe_direction_out.htm
old-project: wdf
ms.assetid: 404e1893-8ee2-429c-b7e3-e6d8d01eaa1c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_USB_PIPE_DIRECTION_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_USB_PIPE_DIRECTION_OUT
req.alt-loc: None,None.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# WDF_USB_PIPE_DIRECTION_OUT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_USB_PIPE_DIRECTION_OUT</b> function determines whether a specified USB endpoint is an output endpoint.


## -syntax

````
BOOLEAN WDF_USB_PIPE_DIRECTION_OUT(
  _In_ UCHAR EndpointAddress
);
````


## -parameters

### -param EndpointAddress [in]

A USB endpoint address.

## -returns
<b>WDF_USB_PIPE_DIRECTION_OUT</b> returns <b>TRUE</b> if the specified endpoint is an output endpoint. Otherwise, this function returns <b>FALSE</b>.

## -remarks
The high bit of the endpoint address determines the direction (input or output) of an endpoint. For more information about endpoint addresses, see the USB specification.

For more information about the <b>WDF_USB_PIPE_DIRECTION_OUT</b> function and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>None</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_usb_pipe_direction_in">WDF_USB_PIPE_DIRECTION_IN</a>
</dt>
<dt>
<a href="wdf.wdfusbtargetpipeisoutendpoint">WdfUsbTargetPipeIsOutEndpoint</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_PIPE_DIRECTION_OUT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>