---
UID: NE.wdm._IRQ_DEVICE_POLICY
title: IRQ_DEVICE_POLICY
author: windows-driver-content
description: The IRQ_DEVICE_POLICY enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.
old-location: kernel\irq_device_policy.htm
old-project: kernel
ms.assetid: 1a605eed-d9a1-4a2f-a095-3e790061527b
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRQ_DEVICE_POLICY
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# IRQ_DEVICE_POLICY enumeration



## -description
<p>The <b>IRQ_DEVICE_POLICY</b> enumeration type indicates the policy the operating system can use to assign the interrupts from a device to different processors.</p>


## -syntax

````
typedef enum _IRQ_DEVICE_POLICY { 
  IrqPolicyMachineDefault                     = 0,
  IrqPolicyAllCloseProcessors                 = 1,
  IrqPolicyOneCloseProcessor                  = 2,
  IrqPolicyAllProcessorsInMachine             = 3,
  IrqPolicySpecifiedProcessors                = 4,
  IrqPolicySpreadMessagesAcrossAllProcessors  = 5
} IRQ_DEVICE_POLICY, *PIRQ_DEVICE_POLICY;
````


## -enum-fields
<dl>

### -field IrqPolicyMachineDefault

<dd>
<p>The device does not require any particular assignment of interrupts to processors.</p>
</dd>

### -field IrqPolicyAllCloseProcessors

<dd>
<p>The operating system should assign interrupts from the device to processors that are close to the device. On non-NUMA computers, the effect of this value is identical to that of <b>IrqPolicyAllProcessorsInMachine</b>.</p>
</dd>

### -field IrqPolicyOneCloseProcessor

<dd>
<p>The operating system should assign a single interrupt for the device to one processor that is close to the device. On non-NUMA computers, the operating system can assign the interrupt to any processor.</p>
</dd>

### -field IrqPolicyAllProcessorsInMachine

<dd>
<p>The operating system should assign interrupts from the device to all processors.</p>
</dd>

### -field IrqPolicySpecifiedProcessors

<dd>
<p>The operating system should assign interrupts from the device to a specific set of processors.</p>
</dd>

### -field IrqPolicySpreadMessagesAcrossAllProcessors

<dd>
<p>The operating system should assign different message-signaled interrupts to different processors, if possible. </p>
</dd>
</dl>

## -remarks
<p>The <b>Interrupt.AffinityPolicy</b> member of the <a href="..\wdm\ns-wdm--io-resource-descriptor.md">IO_RESOURCE_DESCRIPTOR</a> structure is an <b>IRQ_DEVICE_POLICY</b> enumeration value.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\wdm\ns-wdm--io-resource-descriptor.md">IO_RESOURCE_DESCRIPTOR</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IRQ_DEVICE_POLICY enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>