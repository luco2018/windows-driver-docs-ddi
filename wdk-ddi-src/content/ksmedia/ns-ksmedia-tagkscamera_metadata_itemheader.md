---
UID: NS.KSMEDIA.TAGKSCAMERA_METADATA_ITEMHEADER
title: tagKSCAMERA_METADATA_ITEMHEADER
author: windows-driver-content
description: This structure contains the metadata header information that is filled by the camera driver.
old-location: stream\kscamera_metadata_itemheader.htm
old-project: stream
ms.assetid: B4AC04D7-9F98-41F1-A38D-927F3F3A7699
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: tagKSCAMERA_METADATA_ITEMHEADER, KSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSCAMERA_METADATA_ITEMHEADER
req.alt-loc: ksmedia.h
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
---

# tagKSCAMERA_METADATA_ITEMHEADER structure



## -description
This structure contains the metadata header information that is filled by the camera driver.


## -syntax

````
typedef struct tagKSCAMERA_METADATA_ITEMHEADER {
  ULONG MetadataId;
  ULONG Size;
} KSCAMERA_METADATA_ITEMHEADER, *PKSCAMERA_METADATA_ITEMHEADER;
````


## -struct-fields

### -field MetadataId

The identifier for the metadata item. This can be a standard identifier as defined in the <a href="..\ksmedia\ne-ksmedia-kscamera_metadataid.md">KSCAMERA_MetadataId</a> enumeration or any custom metadata identifier that starts from MetadataId_Custom_Start (0x80000000).

### -field Size

Set to <b>sizeof(KSCAMERA_METADATA_ITEMHEADER)</b> + the size of the metadata payload that follows.

## -remarks
This structure along with the metadata payload that follows must be 8-byte aligned.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ksmedia.h</dt>
</dl>
</td>
</tr>
</table>