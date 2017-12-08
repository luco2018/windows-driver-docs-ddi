---
UID: NN.wudfddi.IPowerPolicyCallbackWakeFromSx~r1
title: IPowerPolicyCallbackWakeFromSx
author: windows-driver-content
description: A driver's IPowerPolicyCallbackWakeFromSx interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake both itself and the system from a low-power state.
old-location: wdf\ipowerpolicycallbackwakefromsx.htm
old-project: wdf
ms.assetid: dac93565-e67a-44a3-acf0-e1f58ce8dd9e
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, *PPOWER_ACTION, POWER_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IPowerPolicyCallbackWakeFromSx
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromSx interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
A driver's <b>IPowerPolicyCallbackWakeFromSx</b> interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake both itself and the system from a low-power state.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPowerPolicyCallbackWakeFromSx</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPowerPolicyCallbackWakeFromSx</b> also has these types of members:

The <b>IPowerPolicyCallbackWakeFromSx</b> interface has these methods.

A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx">OnArmWakeFromSx</a> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and the system to enter its working state (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx">OnDisarmWakeFromSx</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.

A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">OnWakeFromSxTriggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.

 

## -members
The <b>IPowerPolicyCallbackWakeFromSx</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx">OnArmWakeFromSx</a> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and the system to enter its working state (S0). 
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx">OnDisarmWakeFromSx</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">OnWakeFromSxTriggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.
</td>
</tr>
</table>A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx">OnArmWakeFromSx</a> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and the system to enter its working state (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx">OnDisarmWakeFromSx</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.

A driver's <a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">OnWakeFromSxTriggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.

 

## -remarks
If your driver supports an <b>IPowerPolicyCallbackWakeFromSx</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> must return the interface. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support
</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
1.9
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>