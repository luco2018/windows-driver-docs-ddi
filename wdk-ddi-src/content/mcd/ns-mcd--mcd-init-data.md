---
UID: NS.mcd._MCD_INIT_DATA
title: MCD_INIT_DATA
author: windows-driver-content
description: The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver.
old-location: storage\mcd_init_data.htm
old-project: storage
ms.assetid: 4fc4c36f-a2ad-4b9f-a30b-e7ed600c38e9
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: MCD_INIT_DATA, MCD_INIT_DATA, *PMCD_INIT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: mcd.h
req.include-header: Mcd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MCD_INIT_DATA
req.alt-loc: mcd.h
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

# MCD_INIT_DATA structure



## -description
<p>The changer miniclass driver fills the MCD_INIT_DATA structure with pointers to its internal command processing routines and passes them to the changer class driver. </p>


## -syntax

````
typedef struct _MCD_INIT_DATA {
  ULONG                       InitDataSize;
  CHANGER_EXTENSION_SIZE      ChangerAdditionalExtensionSize;
  CHANGER_INITIALIZE          ChangerInitialize;
  CHANGER_ERROR_ROUTINE       ChangerError;
  CHANGER_PERFORM_DIAGNOSTICS ChangerPerformDiagnostics;
  CHANGER_COMMAND_ROUTINE     ChangerGetParameters;
  CHANGER_COMMAND_ROUTINE     ChangerGetStatus;
  CHANGER_COMMAND_ROUTINE     ChangerGetProductData;
  CHANGER_COMMAND_ROUTINE     ChangerSetAccess;
  CHANGER_COMMAND_ROUTINE     ChangerGetElementStatus;
  CHANGER_COMMAND_ROUTINE     ChangerInitializeElementStatus;
  CHANGER_COMMAND_ROUTINE     ChangerSetPosition;
  CHANGER_COMMAND_ROUTINE     ChangerExchangeMedium;
  CHANGER_COMMAND_ROUTINE     ChangerMoveMedium;
  CHANGER_COMMAND_ROUTINE     ChangerReinitializeUnit;
  CHANGER_COMMAND_ROUTINE     ChangerQueryVolumeTags;
} MCD_INIT_DATA, *PMCD_INIT_DATA;
````


## -struct-fields
<dl>

### -field InitDataSize

<dd>
<p>Size of this structure in bytes. </p>
</dd>

### -field ChangerAdditionalExtensionSize

<dd>
<p>Pointer to changer miniclass driver routine that returns the number of bytes the changer miniclass driver requires to store device-specific information in the device extension. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
ULONG
(*CHANGER_EXTENSION_SIZE)(
  IN VOID
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerInitialize

<dd>
<p>Pointer to changer miniclass driver routine that does miniclass driver-specific initialization and readies the changer to receive other requests. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef 
NTSTATUS
(*CHANGER_INITIALIZE)(
  IN PDEVICE_OBJECT  DeviceObject
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerError

<dd>
<p>Pointer to changer miniclass driver routine that does device-specific error processing. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*CHANGER_ERROR_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PSCSI_REQUEST_BLOCK  Srb,
  IN NTSTATUS  *Status,
  IN BOOLEAN  *Retry
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerPerformDiagnostics

<dd>
<p>Pointer to changer miniclass driver routine that performs diagnostic tests on the device. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef 
NTSTATUS
(*CHANGER_PERFORM_DIAGNOSTICS)(
  IN PDEVICE_OBJECT  DeviceObject,
  OUT PWMI_CHANGER_PROBLEM_DEVICE_ERROR  changerDeviceError
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerGetParameters

<dd>
<p>Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-parameters.md">IOCTL_CHANGER_GET_PARAMETERS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerGetStatus

<dd>
<p>Pointer to changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-status.md">IOCTL_CHANGER_GET_STATUS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerGetProductData

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-product-data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerSetAccess

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-access.md">IOCTL_CHANGER_SET_ACCESS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerGetElementStatus

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-element-status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerInitializeElementStatus

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-initialize-element-status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerSetPosition

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-position.md">IOCTL_CHANGER_SET_POSITION</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerExchangeMedium

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-exchange-medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerMoveMedium

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-move-medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerReinitializeUnit

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-reinitialize-transport.md">IOCTL_CHANGER_REINITIALIZE_TRANSPORT</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>

### -field ChangerQueryVolumeTags

<dd>
<p>Pointer to a changer miniclass driver routine that handles the device-specific aspects of a device-control IRP with the IOCTL code of <a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-query-volume-tags.md">IOCTL_CHANGER_QUERY_VOLUME_TAGS</a>. This routine has the following prototype:</p>
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
NTSTATUS
(*CHANGER_COMMAND_ROUTINE)(
  IN PDEVICE_OBJECT  DeviceObject,
  IN PIRP  Irp
  );</pre>
</td>
</tr>
</table></span></div>
</dd>
</dl>

## -remarks
<p>This structure is used by the changer driver in Windows XP and later operating systems only. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Mcd.h (include Mcd.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\mcd\nf-mcd-changeradditionalextensionsize.md">ChangerAdditionalExtensionSize</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerinitialize.md">ChangerInitialize</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changererror.md">ChangerError</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerperformdiagnostics.md">ChangerPerformDiagnostics</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetparameters.md">ChangerGetParameters</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetstatus.md">ChangerGetStatus</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetproductdata.md">ChangerGetProductData</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changersetaccess.md">ChangerSetAccess</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changersetposition.md">ChangerSetPosition</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changermovemedium.md">ChangerMoveMedium</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerreinitializeunit.md">ChangerReinitializeUnit</a>
</dt>
<dt>
<a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-parameters.md">IOCTL_CHANGER_GET_PARAMETERS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-status.md">IOCTL_CHANGER_GET_STATUS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-product-data.md">IOCTL_CHANGER_GET_PRODUCT_DATA</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-access.md">IOCTL_CHANGER_SET_ACCESS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-get-element-status.md">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-initialize-element-status.md">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-set-position.md">IOCTL_CHANGER_SET_POSITION</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-exchange-medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>
</dt>
<dt>
<a href="..\ntddchgr\ni-ntddchgr-ioctl-changer-move-medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MCD_INIT_DATA structure%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>