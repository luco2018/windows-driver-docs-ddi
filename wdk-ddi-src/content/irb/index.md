# Irb.h header


This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Irb.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [AtaPortAllocateQueueTag function](nf-irb-ataportallocatequeuetag.md) | The AtaPortAllocateQueueTag routine returns a queue tag for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortBuildRequestSenseIrb function](nf-irb-ataportbuildrequestsenseirb.md) | The AtaPortBuildRequestSenseIrb routine builds and returns an IRB for operation code SCSIOP_REQUEST_SENSE.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortBusChangeDetected function](nf-irb-ataportbuschangedetected.md) | The AtaPortBusChangeDetected routine notifies the port driver of changes in the device configuration on the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortCompleteAllActiveRequests function](nf-irb-ataportcompleteallactiverequests.md) | The AtaPortCompleteAllActiveRequests routine completes all active IRBs for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortCompleteRequest function](nf-irb-ataportcompleterequest.md) | The AtaPortCompleteRequest routine completes the indicated IRB. |
| [AtaPortControllerSyncRoutine function](nf-irb-ataportcontrollersyncroutine.md) | The AtaPortControllerSyncRoutine routine provides synchronized access to data structures that are shared across all channels on a controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortConvertPhysicalAddressToUlong function](nf-irb-ataportconvertphysicaladdresstoulong.md) | The AtaPortConvertPhysicalAddressToUlong routine truncates an address of type IDE_PHYSICAL_ADDRESS to a ULONG.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortConvertUlongToPhysicalAddress function](nf-irb-ataportconvertulongtophysicaladdress.md) | The AtaPortConvertUlongToPhysicalAddress routine converts a given ULONG address into a value of type IDE_PHYSICAL_ADDRESS.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortCopyMemory function](nf-irb-ataportcopymemory.md) | The AtaPortCopyMemory routine copies data from one location to another.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortDebugPrint function](nf-irb-ataportdebugprint.md) | The AtaPortDebugPrint routine passes a message string to the kernel debugger for the debugger to print. |
| [AtaPortDeviceBusy function](nf-irb-ataportdevicebusy.md) | The AtaPortDeviceBusy routine informs the port driver that the indicated device is busy. |
| [AtaPortDeviceReady function](nf-irb-ataportdeviceready.md) | The AtaPortDeviceReady routine informs the port driver that the indicated device is ready to accept new requests. |
| [AtaPortGetBusData function](nf-irb-ataportgetbusdata.md) | The AtaPortGetBusData routine retrieves data from the location that is specified by ConfigDataOffset within the device's PCI configuration space.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortGetDeviceBase function](nf-irb-ataportgetdevicebase.md) | The AtaPortGetDeviceBase routine returns a mapped logical base address that is used to communicate with an HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortGetPhysicalAddress function](nf-irb-ataportgetphysicaladdress.md) | The AtaPortGetPhysicalAddress routine converts the virtual address range to the physical address range. |
| [AtaPortGetScatterGatherList function](nf-irb-ataportgetscattergatherlist.md) | The AtaPortGetScatterGatherList routine retrieves the scatter/gather list that is associated with this request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortGetUnCachedExtension function](nf-irb-ataportgetuncachedextension.md) | The AtaPortGetUncachedExtension routine allocates an uncached common buffer that is shared by the CPU and the device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortInitializeEx function](nf-irb-ataportinitializeex.md) | The AtaPortInitializeEx ATA port driver library routine initializes the port and miniport drivers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortInitializeQueueTag function](nf-irb-ataportinitializequeuetag.md) | The AtaPortInitializeQueueTag routine initializes the queue tag list for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortMoveMemory function](nf-irb-ataportmovememory.md) | The AtaPortMoveMemory routine copies data from one location to another.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortBufferUchar function](nf-irb-ataportreadportbufferuchar.md) | The AtaPortReadPortBufferUchar routine transfers a given number of unsigned byte values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortBufferUlong function](nf-irb-ataportreadportbufferulong.md) | The AtaPortReadPortBufferUlong routine transfers a given number of ULONG values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortBufferUshort function](nf-irb-ataportreadportbufferushort.md) | The AtaPortReadPortBufferUshort routine transfers a given number of USHORT values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortUchar function](nf-irb-ataportreadportuchar.md) | The AtaPortReadPortUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortUlong function](nf-irb-ataportreadportulong.md) | The AtaPortReadPortUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadPortUshort function](nf-irb-ataportreadportushort.md) | The AtaPortReadPortUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterBufferUchar function](nf-irb-ataportreadregisterbufferuchar.md) | The AtaPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterBufferUlong function](nf-irb-ataportreadregisterbufferulong.md) | The AtaPortReadRegisterBufferUlong routine transfers a specified number of ULONG values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterBufferUshort function](nf-irb-ataportreadregisterbufferushort.md) | The AtaPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterUchar function](nf-irb-ataportreadregisteruchar.md) | The AtaPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterUlong function](nf-irb-ataportreadregisterulong.md) | The AtaPortReadRegisterUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReadRegisterUshort function](nf-irb-ataportreadregisterushort.md) | The AtaPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortRegistryAllocateBuffer function](nf-irb-ataportregistryallocatebuffer.md) | The AtaPortRegistryAllocateBuffer routine allocates a buffer for registry operations.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortRegistryChannelSubkeyRead function](nf-irb-ataportregistrychannelsubkeyread.md) | The AtaPortRegistryChannelSubKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel. Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [AtaPortRegistryChannelSubkeyWrite function](nf-irb-ataportregistrychannelsubkeywrite.md) | The AtaPortRegistryChannelSubKeyWrite routine writes data to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel. |
| [AtaPortRegistryChannelSubkeyWriteDeferred function](nf-irb-ataportregistrychannelsubkeywritedeferred.md) | The AtaPortRegistryChannelSubKeyWriteDeferred routine writes data asynchronously to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN\ChannelM, where N is the number of the controller and M is the number of the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [AtaPortRegistryControllerKeyRead function](nf-irb-ataportregistrycontrollerkeyread.md) | The AtaPortRegistryControllerKeyRead routine reads the data that is associated with the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [AtaPortRegistryControllerKeyWrite function](nf-irb-ataportregistrycontrollerkeywrite.md) | The AtaPortRegistryControllerKeyWrite routine writes the data to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller. |
| [AtaPortRegistryControllerKeyWriteDeferred function](nf-irb-ataportregistrycontrollerkeywritedeferred.md) | The AtaPortRegistryControllerKeyWriteDeferred routine writes the data asynchronously to the indicated value name under the registry key HKLM\CurrentControlSet\Services\&lt;service name&gt;\ControllerN, where N is the number of the controller. |
| [AtaPortRegistryFreeBuffer function](nf-irb-ataportregistryfreebuffer.md) | The AtaPortRegistryFreeBuffer routine frees the registry buffer that was allocated by using AtaPortRegistryAllocateBuffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReleaseQueueTag function](nf-irb-ataportreleasequeuetag.md) | The AtaPortReleaseQueueTag routine releases the specified queue tag.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortReleaseRequestSenseIrb function](nf-irb-ataportreleaserequestsenseirb.md) | The AtaPortReleaseRequestSenseIrb routine frees the request sense IRB tha is allocated by using AtaPortBuildRequestSenseIrb. |
| [AtaPortRequestPowerStateChange function](nf-irb-ataportrequestpowerstatechange.md) | The AtaPortRequestPowerStateChange routine requests a power state transition for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortRequestSynchronizedRoutine function](nf-irb-ataportrequestsynchronizedroutine.md) | The AtaPortRequestSynchronizedRoutine routine is used by the miniport driver to request synchronization with the interrupt service routine (ISR).Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortRequestTimer function](nf-irb-ataportrequesttimer.md) | The AtaPortRequestTimer routine requests a timer callback.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortRequestWorkerRoutine function](nf-irb-ataportrequestworkerroutine.md) | The AtaPortRequestWorkerRoutine routine requests a worker routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortSetBusData function](nf-irb-ataportsetbusdata.md) | The AtaPortSetBusData routine stores the data at Buffer in the indicated device's PCI configuration space at an offset that is specified in ConfigDataOffset.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |
| [AtaPortStallExecution function](nf-irb-ataportstallexecution.md) | The AtaPortStallExecution stalls in the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortBufferUchar function](nf-irb-ataportwriteportbufferuchar.md) | The AtaPortWritePortBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortBufferUlong function](nf-irb-ataportwriteportbufferulong.md) | The AtaPortWritePortBufferUlong routine transfers the indicated number of ULONG values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortBufferUshort function](nf-irb-ataportwriteportbufferushort.md) | The AtaPortWritePortBufferUshort routine transfers the indicated number of USHORT values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortUchar function](nf-irb-ataportwriteportuchar.md) | The AtaPortWritePortUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortUlong function](nf-irb-ataportwriteportulong.md) | The AtaPortWritePortUlong routine transfers a ULONG value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWritePortUshort function](nf-irb-ataportwriteportushort.md) | The AtaPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterBufferUchar function](nf-irb-ataportwriteregisterbufferuchar.md) | The AtaPortWriteRegisterBufferUchar routine transfers the indicated number of unsigned bytes from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterBufferUlong function](nf-irb-ataportwriteregisterbufferulong.md) | The AtaPortWriteRegisterBufferUlong routine transfers the indicated number of ULONG values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterBufferUshort function](nf-irb-ataportwriteregisterbufferushort.md) | The AtaPortWriteRegisterBufferUshort routine transfers the indicated number of USHORT values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterUchar function](nf-irb-ataportwriteregisteruchar.md) | The AtaPortWriteRegisterUchar routine transfers an unsigned byte to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterUlong function](nf-irb-ataportwriteregisterulong.md) | The AtaPortWriteRegisterUlong routine transfers a ULONG value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [AtaPortWriteRegisterUshort function](nf-irb-ataportwriteregisterushort.md) | The AtaPortWriteRegisterUshort routine transfers a USHORT value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [IDE_ADAPTER_CONTROL callback](nc-irb-ide-adapter-control.md) | The AtaAdapterControl miniport driver routine is called to perform Plug and Play (PnP) and Power Management operations on the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CHANNEL_ENABLED callback](nc-irb-ide-channel-enabled.md) | The AtaControllerChannelEnabled miniport driver routine indicates whether the specified channel is enabled.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CHANNEL_INIT callback](nc-irb-ide-channel-init.md) | The AtaChannelInitRoutine miniport driver routine initializes the miniport driver's channel interface.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_HW_BUILDIO callback](nc-irb-ide-hw-buildio.md) | The IdeHwBuildIo miniport driver routine is called one time for every incoming I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_HW_CONTROL callback](nc-irb-ide-hw-control.md) | The IdeHwControl miniport driver routine notifies the miniport driver about Plug and Play (PnP) and power events.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_HW_INITIALIZE callback](nc-irb-ide-hw-initialize.md) | The IdeHwInitialize miniport driver routine configures the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_HW_INTERRUPT callback](nc-irb-ide-hw-interrupt.md) | The IdeHwInterrupt miniport driver routine handles interrupts from the host bus adapter (HBA) to which the controller for the miniport driver is connected. |
| [IDE_HW_RESET callback](nc-irb-ide-hw-reset.md) | The IdeHwReset miniport driver routine resets the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_HW_STARTIO callback](nc-irb-ide-hw-startio.md) | The IdeHwStartIo miniport driver routine processes the synchronized aspects of an I/O request.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_TRANSFER_MODE_SELECT callback](nc-irb-ide-transfer-mode-select.md) | The AtaControllerTransferModeSelect miniport driver routine selects the transfer mode for all devices on the indicated ATA channel and programs the controller for the selected transfer mode.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [IDEREGISTERS structure](ns-irb--ideregisters.md) | The IDEREGISTERS structure is used to report the contents of the IDE controller registers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_ACCESS_RANGE structure](ns-irb--ide-access-range.md) | The IDE_ACCESS_RANGE structure contains the address ranges allocated for an IDE controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CHANNEL_CONFIGURATION structure](ns-irb--ide-channel-configuration.md) | The IDE_CHANNEL_CONFIGURATION structure contains configuration information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CHANNEL_INTERFACE structure](ns-irb--ide-channel-interface.md) | The IDE_CHANNEL_INTERFACE structure contains interface information for the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CONTROLLER_CONFIGURATION structure](ns-irb--ide-controller-configuration.md) | The IDE_CONTROLLER_CONFIGURATION structure is used to pass controller configuration information between the port driver and the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CONTROLLER_INTERFACE structure](ns-irb--ide-controller-interface.md) | The IDE_CONTROLLER_INTERFACE structure is used to pass controller configuration information between the port driver and the miniport driver.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_DEVICE_PARAMETERS structure](ns-irb--ide-device-parameters.md) | The IDE_DEVICE_PARAMETERS structure contains configuration information that the port driver provides to the miniport driver to configure a device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_LBA_RANGE structure](ns-irb--ide-lba-range.md) | The IDE_LBA_RANGE structure is used by the port driver to provide the miniport driver with a range of logical blocks.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_MINIPORT_RESOURCES structure](ns-irb--ide-miniport-resources.md) | The IDE_MINIPORT_RESOURCES structure is used by the port driver to provide the miniport driver with resources.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_POWER_INFO structure](ns-irb--ide-power-info.md) | The POWER_CHANGE_INFO structure is used in conjunction with the IDE_REQUEST_BLOCK to request a power state change.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_REQUEST_BLOCK structure](ns-irb--ide-request-block.md) | The IDE_REQUEST_BLOCK structure defines an IDE request block.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_TASK_FILE structure](ns-irb--ide-task-file.md) | The IDE_TASK_FILE structure contains the current and previous IDE task file.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_TRANSFER_MODE_PARAMETERS structure](ns-irb--ide-transfer-mode-parameters.md) | The IDE_TRANSFER_MODE_PARAMETERS structure is used in conjunction with the miniport driver's AtaControllerTransferModeSelect routine to set the transfer mode parameters on a channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [ATA_ADDRESS_TRANSLATION enumeration](ne-irb-ata-address-translation.md) | The ATA_ADDRESS_TRANSLATION enumeration type indicates the type of address translation used during data transfers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [ATA_CHANNEL_STATE enumeration](ne-irb-ata-channel-state.md) | The ATA_CHANNEL_STATE enumeration type indicates the state of the channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_CONTROL_ACTION enumeration](ne-irb-ide-control-action.md) | The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a IdeHwControl routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_DEVICE_TYPE enumeration](ne-irb-ide-device-type.md) | The IDE_DEVICE_TYPE enumeration type indicates the device type.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. |
| [IDE_POWER_STATE enumeration](ne-irb-ide-power-state.md) | The IDE_POWER_STATE enumeration type indicates that power state of the device. |