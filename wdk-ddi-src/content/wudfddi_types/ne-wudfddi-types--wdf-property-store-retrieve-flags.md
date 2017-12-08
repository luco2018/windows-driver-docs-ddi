---
UID: NE.wudfddi_types._WDF_PROPERTY_STORE_RETRIEVE_FLAGS
title: WDF_PROPERTY_STORE_RETRIEVE_FLAGS
author: windows-driver-content
description: The WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration contains values that indicate whether UMDF should create a registry key if the key does not already exist.
old-location: wdf\wdf_property_store_retrieve_flags.htm
old-project: wdf
ms.assetid: bd64ef0d-b2e7-4f82-87a8-77fe98677fd9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WRITE_REGISTER_USHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDF_PROPERTY_STORE_RETRIEVE_FLAGS
req.alt-loc: Wudfddi_types.h
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
req.product: Windows 10 or later.
---

# WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration contains values that indicate whether  UMDF should create a registry key if the key does not already exist.</p>


## -syntax

````
typedef enum _WDF_PROPERTY_STORE_RETRIEVE_FLAGS { 
  WdfPropertyStoreNormal              = 0,
  WdfPropertyStoreCreateIfMissing     = 0x1,
  WdfPropertyStoreCreateVolatile      = 0x2,
  WdfPropertyStoreRetrieveFlagsMask   = WdfPropertyStoreNormal |
                                      WdfPropertyStoreCreateIfMissing |
                                      WdfPropertyStoreCreateVolatile

} WDF_PROPERTY_STORE_RETRIEVE_FLAGS;
````


## -enum-fields
<dl>

### -field WdfPropertyStoreNormal

<dd>
<p>Do not create the registry key if it does not exist.</p>
</dd>

### -field WdfPropertyStoreCreateIfMissing

<dd>
<p>Create the registry key if it does not exist. The key will be <i>nonvolatile</i>, which means that it will not be deleted when Windows restarts.</p>
</dd>

### -field WdfPropertyStoreCreateVolatile 

<dd>
<p>Create the registry key if it does not exist. The key will be volatile, which means that it will be deleted when Windows restarts. This flag is available in UMDF versions 1.9 and later. </p>
</dd>

### -field WdfPropertyStoreRetrieveFlagsMask 

<dd>
<p>Reserved for system use. </p>
</dd>
</dl>

## -remarks
<p><b>WDF_PROPERTY_STORE_RETRIEVE_FLAGS</b> enumeration values are used as input to the <a href="wdf.iwdfdevice_retrievedevicepropertystore">IWDFDevice::RetrieveDevicePropertyStore</a>, <a href="wdf.iwdfdeviceinitialize_retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>, and <a href="wdf.iwdfpropertystorefactory_retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a> methods.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfdevice_retrievedevicepropertystore">IWDFDevice::RetrieveDevicePropertyStore</a>
</dt>
<dt>
<a href="wdf.iwdfdeviceinitialize_retrievedevicepropertystore">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>
</dt>
<dt>
<a href="wdf.iwdfpropertystorefactory_retrievedevicepropertystore">IWDFPropertyStoreFactory::RetrieveDevicePropertyStore</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_PROPERTY_STORE_RETRIEVE_FLAGS enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>