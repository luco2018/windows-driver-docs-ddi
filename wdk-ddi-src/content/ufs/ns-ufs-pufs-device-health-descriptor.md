---
UID: NS.ufs.PUFS_DEVICE_HEALTH_DESCRIPTOR
title: PUFS_DEVICE_HEALTH_DESCRIPTOR
author: windows-driver-content
description: The UFS_DEVICE_HEALTH_DESCRIPTOR structure describes the health of a device.
old-location: storage\ufs_device_health_descriptor.htm
old-project: storage
ms.assetid: 6B085DBB-2AAA-4170-A2B1-EA4D2C207A24
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: PUFS_DEVICE_HEALTH_DESCRIPTOR, UFS_DEVICE_HEALTH_DESCRIPTOR, *PUFS_DEVICE_HEALTH_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UFS_DEVICE_HEALTH_DESCRIPTOR
req.alt-loc: Ufs.h
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
req.product: Windows 10 or later.
---

# PUFS_DEVICE_HEALTH_DESCRIPTOR structure



## -description
<p>The <b>UFS_DEVICE_HEALTH_DESCRIPTOR</b> structure describes the health of a device. </p>


## -syntax

````
typedef struct _UFS_DEVICE_HEALTH_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bPreEOLInfo;
  UCHAR bDeviceLifeTimeEstA;
  UCHAR bDeviceLifeTimeEstB;
  UCHAR VendorPropInfo[32];
} UFS_DEVICE_HEALTH_DESCRIPTOR, *PUFS_DEVICE_HEALTH_DESCRIPTOR;
````


## -struct-fields
<dl>

### -field bLength

<dd>
<p>Specifies the length, in bytes, of this descriptor.</p>
</dd>

### -field bDescriptorIDN

<dd>
<p>Specifies the descriptor's Identification value. <b>UFS_DEVICE_HEALTH_DESCRIPTOR </b>will have a value of <b>UFS_DESC_HEALTH_IDN</b>.</p>
</dd>

### -field bPreEOLInfo

<dd>
<p>Contains Pre-End of Life Information. This member supplies information about a device's life time as reflected by the average number of reserved blocks. Contains one of the following values:</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Member is not defined.</td>
</tr>
<tr>
<td>0x01</td>
<td>Normal. Consumed less than 80% of reserved blocks.</td>
</tr>
<tr>
<td>0x02</td>
<td>Consumed 80% of
reserved blocks.</td>
</tr>
<tr>
<td>0x03</td>
<td>Critical. Consumed 90% of
reserved blocks.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bDeviceLifeTimeEstA

<dd>
<p><b>bDeviceLifeTimeEstA</b> provides an estimation of how much of a device's estimated life time has been used based on the amount of performed program/erase cycles. This calculation is vendor-specific and is referred as method A. Contains one of the following values:</p>
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>0x00</td>
<td>Information about device's life time not found.</td>
</tr>
<tr>
<td>0x01</td>
<td>0% to 10% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x02</td>
<td>10% to 20% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x03</td>
<td>20% to 30% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x04</td>
<td>30% to 40% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x05</td>
<td>40% to 50% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x06</td>
<td>50% to 60% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x07</td>
<td>60% to 70% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x08</td>
<td>70% to 80% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x09</td>
<td>80% to 90% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x0A</td>
<td>90% to 100% of the device's estimated life time has been used.</td>
</tr>
<tr>
<td>0x0B</td>
<td>Device has exceeded it's estimated life time.</td>
</tr>
<tr>
<td>All other values</td>
<td>Reserved for future use.</td>
</tr>
</table>
<p> </p>
</dd>

### -field bDeviceLifeTimeEstB

<dd>
<p><b>bDeviceLifeTimeEstB</b> provides an estimation of how much of a device's estimated life time has been used based on the amount of performed program/erase cycles. This calculation is vendor-specific and is referred as method B. Contains the same possible values as <b>bDeviceLifeTimeEstA</b>.</p>
</dd>

### -field VendorPropInfo[32]

<dd>
<p>Reserved for vendor use.</p>
</dd>
</dl>

## -remarks
<p>The UFS Host Controller contains a series of configurable Descriptor Tables, which allow the driver to query and configure the host controller’s capabilities. Query the Requested Descriptor from the Descriptor Table on the device.</p>

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
<dt>Ufs.h</dt>
</dl>
</td>
</tr>
</table>