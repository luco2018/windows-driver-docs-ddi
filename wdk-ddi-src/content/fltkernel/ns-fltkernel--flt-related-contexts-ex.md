---
UID: NS.fltkernel._FLT_RELATED_CONTEXTS_EX
title: FLT_RELATED_CONTEXTS_EX
author: windows-driver-content
description: The FLT_RELATED_CONTEXTS_EX structure contains a minifilter driver's contexts for the objects associated with an I/O operation.
old-location: ifsk\flt_related_contexts_ex.htm
old-project: ifsk
ms.assetid: 9D3E77AE-C63D-4253-8520-6A9ACCBB89CC
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FLT_RELATED_CONTEXTS_EX, FLT_RELATED_CONTEXTS_EX, *PFLT_RELATED_CONTEXTS_EX
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FLT_RELATED_CONTEXTS_EX
req.alt-loc: fltkernel.h
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

# FLT_RELATED_CONTEXTS_EX structure



## -description
<p>The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation.  This structure extends the <a href="..\fltkernel\ns-fltkernel--flt-related-contexts.md">FLT_RELATED_CONTEXTS</a> structure to include the section context.</p>


## -syntax

````
typedef struct _FLT_RELATED_CONTEXTS_EX {
  PFLT_CONTEXT VolumeContext;
  PFLT_CONTEXT InstanceContext;
  PFLT_CONTEXT FileContext;
  PFLT_CONTEXT StreamContext;
  PFLT_CONTEXT StreamHandleContext;
  PFLT_CONTEXT TransactionContext;
  PFLT_CONTEXT SectionContext;
} FLT_RELATED_CONTEXTS_EX, *PFLT_RELATED_CONTEXTS_EX;
````


## -struct-fields
<dl>

### -field VolumeContext

<dd>
<p>Opaque pointer to the minifilter's context for the volume that the <b>Volume</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to. </p>
</dd>

### -field InstanceContext

<dd>
<p>Opaque pointer to the minifilter driver's context for the instance that the <b>Instance</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to. </p>
</dd>

### -field FileContext

<dd>
<p>An opaque pointer to the minifilter driver's per-file context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to.</p>
</dd>

### -field StreamContext

<dd>
<p>Opaque pointer to the minifilter's stream context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to. </p>
</dd>

### -field StreamHandleContext

<dd>
<p>Opaque pointer to the minifilter's stream handle context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to. </p>
</dd>

### -field TransactionContext

<dd>
<p>An opaque pointer to the minifilter's transaction context for the transaction that the <b>Transaction</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to.</p>
</dd>

### -field SectionContext

<dd>
<p>An opaque pointer to the minifilter's section context for the stream handle that the <b>FileObject</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a> structure points to.</p>
</dd>
</dl>

## -remarks
<p>The <b>FLT_RELATED_CONTEXTS_EX</b> structure contains a minifilter driver's contexts for the objects associated with an I/O operation or an instance setup or teardown operation. </p>

<p>A minifilter driver uses the <b>FLT_RELATED_CONTEXTS_EX</b> structure to retrieve multiple contexts for a given operation. To do so, the minifilter driver allocates an empty <b>FLT_RELATED_CONTEXTS_EX</b> structure and passes a pointer to it as the <i>Contexts</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltgetcontextsex.md">FltGetContextsEx</a>. </p>

<p>A minifilter can also use this structure to release multiple contexts for a given operation. To do so, the minifilter driver passes a pointer to <b>FLT_RELATED_CONTEXTS_EX</b> as the <i>Contexts</i> parameter to <a href="..\fltkernel\nf-fltkernel-fltreleasecontextsex.md">FltReleaseContextsEx</a>. </p>

<p>For more information about using contexts, see the reference entry for <a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-context-registration.md">FLT_CONTEXT_REGISTRATION</a>
</dt>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-related-objects.md">FLT_RELATED_OBJECTS</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatecontext.md">FltAllocateContext</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltgetcontextsex.md">FltGetContextsEx</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltreleasecontextsex.md">FltReleaseContextsEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FLT_RELATED_CONTEXTS_EX structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>