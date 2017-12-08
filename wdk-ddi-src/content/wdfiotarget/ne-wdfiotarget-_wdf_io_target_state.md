---
UID: NE.wdfiotarget._WDF_IO_TARGET_STATE
title: _WDF_IO_TARGET_STATE
author: windows-driver-content
description: The WDF_IO_TARGET_STATE enumeration specifies the states that an I/O target can be in.
old-location: wdf\wdf_io_target_state.htm
old-project: wdf
ms.assetid: 0189a83d-da46-49f1-99b8-8fb920009804
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_IO_TARGET_STATE, WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.alt-api: WDF_IO_TARGET_STATE
req.alt-loc: wdfiotarget.h,wudfddi_types.h
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
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_STATE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_IO_TARGET_STATE</b> enumeration specifies the states that an I/O target can be in.


## -syntax

````
typedef enum _WDF_IO_TARGET_STATE { 
  WdfIoTargetStateUndefined        = 0,
  WdfIoTargetStarted               = 1,
  WdfIoTargetStopped               = 2,
  WdfIoTargetClosedForQueryRemove  = 3,
  WdfIoTargetClosed                = 4,
  WdfIoTargetDeleted               = 5,
  WdfIoTargetPurged                = 6
} WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE;
````


## -enum-fields

### -field WdfIoTargetStateUndefined

Reserved for internal use.

### -field WdfIoTargetStarted

The I/O target is started and can process I/O requests.

### -field WdfIoTargetStopped

The I/O target is temporarily stopped and cannot process I/O requests.

### -field WdfIoTargetClosedForQueryRemove

The I/O target's underlying device might be removed in the near future.

### -field WdfIoTargetClosed

The I/O target is permanently stopped and cannot process I/O requests. 

### -field WdfIoTargetDeleted

The I/O target's underlying device has been removed.

### -field WdfIoTargetPurged

The I/O target is temporarily purged and cannot receive or process I/O requests. This constant is available starting in KMDF 1.11.

## -remarks
To obtain an I/O target's current state, call <a href="wdf.wdfiotargetgetstate">WdfIoTargetGetState</a>.

For more information about states for I/O targets, see <a href="wdf.controlling_a_general_i_o_target_s_state">Controlling a General I/O Target's State</a>.

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
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfiotarget.h (include Wdf.h); </dt>
<dt>Wudfddi_types.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfiotargetgetstate">WdfIoTargetGetState</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_STATE enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>