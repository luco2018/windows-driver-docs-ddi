---
UID: NS.wmilib._WMILIB_CONTEXT
title: WMILIB_CONTEXT
author: windows-driver-content
description: The WMILIB_CONTEXT structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines.
old-location: kernel\wmilib_context.htm
old-project: kernel
ms.assetid: c9319f35-9745-47c4-a98d-4321e0d39f86
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WMILIB_CONTEXT, WMILIB_CONTEXT, *PWMILIB_CONTEXT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmilib.h
req.include-header: Wmilib.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WMILIB_CONTEXT
req.alt-loc: wmilib.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# WMILIB_CONTEXT structure



## -description
<p>The <b>WMILIB_CONTEXT</b> structure provides registration information for a driver's data blocks and event blocks and defines entry points for the driver's WMI library callback routines. </p>


## -syntax

````
typedef struct _WMILIB_CONTEXT {
  ULONG                 GuidCount;
  PWMIGUIDREGINFO       GuidList;
  PWMI_QUERY_REGINFO    QueryWmiRegInfo;
  PWMI_QUERY_DATABLOCK  QueryWmiDataBlock;
  PWMI_SET_DATABLOCK    SetWmiDataBlock;
  PWMI_SET_DATAITEM     SetWmiDataItem;
  PWMI_EXECUTE_METHOD   ExecuteWmiMethod;
  PWMI_FUNCTION_CONTROL WmiFunctionControl;
} WMILIB_CONTEXT, *PWMILIB_CONTEXT;
````


## -struct-fields
<dl>

### -field GuidCount

<dd>
<p>Specifies the number of blocks registered by the driver.</p>
</dd>

### -field GuidList

<dd>
<p>Pointer to an array of <b>GuidCount</b> <a href="..\wmilib\ns-wmilib--wmiguidreginfo.md">WMIGUIDREGINFO</a> structures that contain registration information for each block.</p>
</dd>

### -field QueryWmiRegInfo

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmiqueryreginfo">DpWmiQueryReginfo</a> routine, which is a required entry point for drivers that call WMI library support routines.</p>
</dd>

### -field QueryWmiDataBlock

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmiquerydatablock">DpWmiQueryDataBlock</a> routine, which is a required entry point for drivers that call WMI library support routines.</p>
</dd>

### -field SetWmiDataBlock

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmisetdatablock">DpWmiSetDataBlock</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_WMI_READ_ONLY to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550831">IRP_MN_CHANGE_SINGLE_INSTANCE</a> request.</p>
</dd>

### -field SetWmiDataItem

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmisetdataitem">DpWmiSetDataItem</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_WMI_READ_ONLY to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550836">IRP_MN_CHANGE_SINGLE_ITEM</a> request.</p>
</dd>

### -field ExecuteWmiMethod

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmiexecutemethod">DpWmiExecuteMethod</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_INVALID_DEVICE_REQUEST to the caller in response to any <a href="https://msdn.microsoft.com/library/windows/hardware/ff550868">IRP_MN_EXECUTE_METHOD</a> request.</p>
</dd>

### -field WmiFunctionControl

<dd>
<p>Pointer to the driver's <a href="kernel.dpwmifunctioncontrol">DpWmiFunctionControl</a> routine, which is an optional entry point for drivers that call WMI library support routines. If the driver does not implement this routine, it must set this member to <b>NULL</b>. In this case, WMI returns STATUS_SUCCESS to the caller in response to any <b>IRP_MN_ENABLE_<i>XXX</i></b> or <b>IRP_MN_DISABLE_<i>XXX</i></b> request.</p>
</dd>
</dl>

## -remarks
<p>A driver that handles WMI IRPs by calling WMI library support routines stores an initialized <b>WMILIB_CONTEXT</b> structure (or a pointer to such a structure) in its device extension. A driver can use the same <b>WMILIB_CONTEXT</b> structure for multiple device objects if each device object supplies the same set of data blocks. </p>

<p>When the driver receives an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550813">IRP_MJ_SYSTEM_CONTROL</a> request, it calls <a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a> with a pointer to its <b>WMILIB_CONTEXT</b> structure, a pointer to its device object, and a pointer to the IRP. <b>WmiSystemControl</b> determines whether the IRP contains a WMI request and, if so, handles the request by calling the driver's appropriate <i>DpWmiXxx</i> routine.</p>

<p>Memory for this structure can be allocated from paged pool.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wmilib.h (include Wmilib.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.dpwmiexecutemethod">DpWmiExecuteMethod</a>
</dt>
<dt>
<a href="kernel.dpwmifunctioncontrol">DpWmiFunctionControl</a>
</dt>
<dt>
<a href="kernel.dpwmiqueryreginfo">DpWmiQueryReginfo</a>
</dt>
<dt>
<a href="kernel.dpwmiquerydatablock">DpWmiQueryDataBlock</a>
</dt>
<dt>
<a href="kernel.dpwmisetdatablock">DpWmiSetDataBlock</a>
</dt>
<dt>
<a href="kernel.dpwmisetdataitem">DpWmiSetDataItem</a>
</dt>
<dt>
<a href="..\wmilib\ns-wmilib--wmiguidreginfo.md">WMIGUIDREGINFO</a>
</dt>
<dt>
<a href="..\wmilib\nf-wmilib-wmisystemcontrol.md">WmiSystemControl</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMILIB_CONTEXT structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>