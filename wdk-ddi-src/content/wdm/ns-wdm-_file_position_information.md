---
UID: NS.WDM._FILE_POSITION_INFORMATION
title: _FILE_POSITION_INFORMATION
author: windows-driver-content
description: The FILE_POSITION_INFORMATION structure is used as an argument to routines that query or set file information.
old-location: kernel\file_position_information.htm
old-project: kernel
ms.assetid: 04f01faf-599e-4c62-82ce-c147b4820c8f
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _FILE_POSITION_INFORMATION, FILE_POSITION_INFORMATION, *PFILE_POSITION_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FILE_POSITION_INFORMATION
req.alt-loc: Wdm.h
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
req.product: Windows 10 or later.
---

# _FILE_POSITION_INFORMATION structure



## -description
The <b>FILE_POSITION_INFORMATION</b> structure is used as an argument to routines that query or set file information.


## -syntax

````
typedef struct _FILE_POSITION_INFORMATION {
  LARGE_INTEGER CurrentByteOffset;
} FILE_POSITION_INFORMATION, *PFILE_POSITION_INFORMATION;
````


## -struct-fields

### -field CurrentByteOffset

The byte offset of the current file pointer.

## -remarks
FILE_READ_DATA or FILE_WRITE_DATA access to the file is required to change this information about the file, and the file must be opened for synchronous I/O.

If the file was opened or created with the FILE_NO_INTERMEDIATE_BUFFERING option, the value of <b>CurrentByteOffset</b> must be an integral multiple of the sector size of the underlying device.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.zwcreatefile">ZwCreateFile</a>
</dt>
<dt>
<a href="kernel.zwsetinformationfile">ZwSetInformationFile</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20FILE_POSITION_INFORMATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>