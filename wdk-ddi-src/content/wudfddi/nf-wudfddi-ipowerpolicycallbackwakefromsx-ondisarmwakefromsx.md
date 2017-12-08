---
UID: NF.wudfddi.IPowerPolicyCallbackWakeFromSx.OnDisarmWakeFromSx
title: IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx
author: windows-driver-content
description: A driver's OnDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\ipowerpolicycallbackwakefromsx_ondisarmwakefromsx.htm
old-project: wdf
ms.assetid: 0e2f42af-3eb7-4957-be91-4f31d2d558c2
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IPowerPolicyCallbackWakeFromSx, OnDisarmWakeFromSx, IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IPowerPolicyCallbackWakeFromSx.OnDisarmWakeFromSx
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
req.iface: IPowerPolicyCallbackWakeFromSx
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>A driver's <b>OnDisarmWakeFromSx</b> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.</p>


## -syntax

````
void OnDisarmWakeFromSx(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters
<dl>

### -param pWdfDevice [in]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface of the device object that represents one of the driver's devices.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>Your driver must provide an <b>OnDisarmWakeFromSx</b> callback function if the driver supports the <a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a> interface. </p>

<p>If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <b>OnDisarmWakeFromSx</b> callback function, the framework calls the driver's <a href="wdf.ipnpcallback_ond0entry">IPnpCallback::OnD0Entry</a> and <a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a> callback functions.</p>

<p>The <b>OnDisarmWakeFromSx</b> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.</p>

<p>For more information about when the framework calls this callback function, see <a href="wdf.pnp_and_power_management_scenarios_in_umdf">PnP and Power Management Scenarios in UMDF</a>.</p>

<p>For more information about this callback function, see <a href="wdf.supporting_system_wake_up_in_umdf_drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.</p>

## -requirements
<table>
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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.9</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a>
</dt>
<dt>
<a href="wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a>
</dt>
<dt>
<a href="wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>