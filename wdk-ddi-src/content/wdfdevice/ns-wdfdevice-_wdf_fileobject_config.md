---
UID: NS.WDFDEVICE._WDF_FILEOBJECT_CONFIG
title: _WDF_FILEOBJECT_CONFIG
author: windows-driver-content
description: The WDF_FILEOBJECT_CONFIG structure contains configuration information of a driver's framework file objects.
old-location: wdf\wdf_fileobject_config.htm
old-project: wdf
ms.assetid: 6fefc35f-fbbd-4c5e-bb8f-25ad3b6cdb67
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_FILEOBJECT_CONFIG, *PWDF_FILEOBJECT_CONFIG, WDF_FILEOBJECT_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_FILEOBJECT_CONFIG
req.alt-loc: wdfdevice.h
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
req.product: Windows 10 or later.
---

# _WDF_FILEOBJECT_CONFIG structure



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_FILEOBJECT_CONFIG</b> structure contains configuration information of a driver's framework file objects. 


## -syntax

````
typedef struct _WDF_FILEOBJECT_CONFIG {
  ULONG                      Size;
  PFN_WDF_DEVICE_FILE_CREATE EvtDeviceFileCreate;
  PFN_WDF_FILE_CLOSE         EvtFileClose;
  PFN_WDF_FILE_CLEANUP       EvtFileCleanup;
  WDF_TRI_STATE              AutoForwardCleanupClose;
  WDF_FILEOBJECT_CLASS       FileObjectClass;
} WDF_FILEOBJECT_CONFIG, *PWDF_FILEOBJECT_CONFIG;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field EvtDeviceFileCreate

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function, or <b>NULL</b>.

### -field EvtFileClose

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a> callback function, or <b>NULL</b>.

### -field EvtFileCleanup

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> callback function, or <b>NULL</b>.

### -field AutoForwardCleanupClose

A <a href="wdf.wdf_tri_state">WDF_TRI_STATE</a>-typed value. For more information about this member, see the following Comments section.

### -field FileObjectClass

A <a href="wdf.wdf_fileobject_class">WDF_FILEOBJECT_CLASS</a>-typed value that identifies whether the driver requires a framework file object to represent each file that an application or another driver creates or opens. Additionally, this value specifies where the framework can store the object's handle. 

## -remarks
The <b>WDF_FILEOBJECT_CONFIG</b> structure is used as input to the <a href="wdf.wdfdeviceinitsetfileobjectconfig">WdfDeviceInitSetFileObjectConfig</a> method.

<b>WDF_FILEOBJECT_CONFIG</b> must be initialized by calling <a href="wdf.wdf_fileobject_config_init">WDF_FILEOBJECT_CONFIG_INIT</a>.

If <b>AutoForwardCleanupClose</b> is set to <b>WdfTrue</b>, the framework does the following:

The framework forwards file creation requests to the next-lower driver if the driver does not provide an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function and has not called <a href="wdf.wdfdeviceconfigurerequestdispatching">WdfDeviceConfigureRequestDispatching</a> to set an I/O queue to receive file creation requests. The framework does not forward file creation requests if the driver provides a callback function or a queue to handle the requests, so the driver must <a href="wdf.forwarding_i_o_requests">forward</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh406719">complete</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/hh406716">cancel</a> the requests.

The framework sends file cleanup and close requests to the next-lower driver after calling the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a> callback functions.

If <b>AutoForwardCleanupClose</b> is set to <b>WdfFalse</b>, the framework does not forward file creation, cleanup, or close requests. Instead, the framework completes the requests for the driver.

If <b>AutoForwardCleanupClose</b> is set to <b>WdfUseDefault</b>, the framework uses <b>WdfTrue</b> behavior for filter drivers and <b>WdfFalse</b> behavior for function drivers.

Your driver's local I/O target must always receive an equal number of I/O requests with request types of <b>WdfRequestTypeCreate</b>, <b>WdfRequestTypeCleanup</b>, and <b>WdfRequestTypeClose</b>. Therefore, if the driver provides either an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_file_create.md">EvtDeviceFileCreate</a> callback function or an I/O queue that receives file creation requests, you must use the following rules:

If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfTrue</b>, the driver must forward all file creation requests to the local I/O target. You must follow this rule because the framework will forward all cleanup and close requests to the local target, whether or not your driver provides <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a> callback functions.

If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfFalse</b>, the driver must <i>not</i> forward file creation requests to the local I/O target. You must follow this rule because the framework will <i>not</i> forward cleanup and close requests to the local target, whether or not your driver provides <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_cleanup.md">EvtFileCleanup</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_file_close.md">EvtFileClose</a> callback functions.

If your driver sets <b>AutoForwardCleanupClose</b> to <b>WdfDefault</b>, the driver must follow the rule for <b>WdfTrue</b> if it is a filter driver. The driver must follow the rule for <b>WdfFalse</b> if it is a function driver.

## -requirements
<table>
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
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>