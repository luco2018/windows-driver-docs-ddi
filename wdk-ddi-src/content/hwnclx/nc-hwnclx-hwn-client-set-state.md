---
UID: NC.hwnclx.HWN_CLIENT_SET_STATE
title: HWN_CLIENT_SET_STATE
author: windows-driver-content
description: Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.
old-location: gpiobtn\hwn_client_set_state.htm
old-project: gpiobtn
ms.assetid: 5d2ccc29-4022-467c-9f37-d49badcceba4
ms.author: windowsdriverdev
ms.date: 10/23/2017
ms.keywords: HPMI_QUERY_CAPABILITIES, HPMI_QUERY_CAPABILITIES, *PHPMI_QUERY_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: hwnclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: *PHWN_CLIENT_SET_STATE
req.alt-loc: Hwnclx.h
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
req.iface: 
---

# HWN_CLIENT_SET_STATE callback



## -description
<p>
Implemented by the client driver to set hardware notification component state. It is invoked when a user wants to change the state of a driver.</p>


## -prototype

````
HWN_CLIENT_SET_STATE HwnClientSetState;

NTSTATUS HwnClientSetState(
  _In_  PVOID  Context,
  _In_  PVOID  Buffer,
  _In_  ULONG  BufferLength,
  _Out_ PULONG BytesWritten
)
{ ... }

typedef HWN_CLIENT_SET_STATE *PHWN_CLIENT_SET_STATE;
````


## -parameters
<dl>

### -param Context [in]

<dd>
<p>Pointer to the client driver's context information. This memory space is available for use by the client driver. It is allocated as part of the framework object context space by <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information, see <a href="gpiobtn.hwn_client_registration_packet">HWN_CLIENT_REGISTRATION_PACKET</a> and  <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.</p>
</dd>

### -param Buffer [in]

<dd>
<p>Buffer of <i>BufferLength</i> bytes containing a <a href="gpiobtn.hwn_header">HWN_HEADER</a> structure including one or more <a href="gpiobtn.hwn_settings">HWN_SETTINGS</a> structures that specify the hardware notifications to be set.</p>
</dd>

### -param BufferLength [in]

<dd>
<p>The size of <i>Buffer</i> in bytes.</p>
</dd>

### -param BytesWritten [out]

<dd>
<p>Pointer to a variable that indicates the number of bytes written by the function.</p>
</dd>
</dl>

## -returns
<p>
Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.</p>

## -remarks
<p>Register your implementation of this callback function by setting the appropriate member of <a href="gpiobtn.hwn_client_registration_packet">HWN_CLIENT_REGISTRATION_PACKET</a> and then calling <a href="..\hwnclx\nf-hwnclx-hwnregisterclient.md">HwNRegisterClient</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10, version 1709</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Hwnclx.h</dt>
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
<dt><a href="https://msdn.microsoft.com/en-us/library/windows/hardware/dn789335">Hardware notifications support</a></dt>
<dt>
<a href="gpiobtn.hardware_notifications_reference">Hardware notifications reference</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [gpiobtn\gpiobtn]:%20HWN_CLIENT_SET_STATE callback function%20 RELEASE:%20(10/23/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>