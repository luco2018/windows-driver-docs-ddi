---
UID: NS.bthddi._INDICATION_PARAMETERS~r1
title: INDICATION_PARAMETERS
author: windows-driver-content
description: The INDICATION_PARAMETERS structure is passed as the Parameters parameter to a profile driver's L2CAP Callback Function.
old-location: bltooth\indication_parameters.htm
old-project: bltooth
ms.assetid: fc93ab8a-01d2-4827-8d89-06f09bf10456
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: INDICATION_PARAMETERS, INDICATION_PARAMETERS, *PINDICATION_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows Vista, and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: INDICATION_PARAMETERS
req.alt-loc: bthddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.iface: IBidiSpl2
---

# INDICATION_PARAMETERS structure



## -description
<p>The INDICATION_PARAMETERS structure is passed as the 
  <i>Parameters</i> parameter to a profile driver's 
  <a href="..\bthddi\nc-bthddi-pfnbthport-indication-callback.md">L2CAP Callback Function</a>.</p>


## -syntax

````
typedef struct _INDICATION_PARAMETERS {
  L2CAP_CHANNEL_HANDLE ConnectionHandle;
  BTH_ADDR             BtAddress;
  union {
    struct {
      struct {
        USHORT PSM;
      } Request;
    } Connect;
    struct {
      CHANNEL_CONFIG_PARAMETERS CurrentParams;
      CHANNEL_CONFIG_PARAMETERS RequestedParams;
      CHANNEL_CONFIG_PARAMETERS ResponseParams;
      USHORT                    Response;
    } ConfigRequest;
    struct {
      CHANNEL_CONFIG_PARAMETERS CurrentParams;
      CHANNEL_CONFIG_PARAMETERS RequestedParams;
      CHANNEL_CONFIG_PARAMETERS RejectedParams;
      PCO_TYPE                  UnknownTypes;
      ULONG                     NumUnknownTypes;
      CHANNEL_CONFIG_PARAMETERS NewRequestParams;
      USHORT                    Response;
    } ConfigResponse;
    struct {
      ULONG                NumExtraOptions;
      PL2CAP_CONFIG_OPTION ExtraOptions;
    } FreeExtraOptions;
    struct {
      L2CAP_DISCONNECT_REASON Reason;
      BOOLEAN                 CloseNow;
    } Disconnect;
    struct {
      ULONG PacketLength;
      ULONG TotalQueueLength;
    } RecvPacket;
  } Parameters;
} INDICATION_PARAMETERS, *PINDICATION_PARAMETERS;
````


## -struct-fields
<dl>

### -field ConnectionHandle

<dd>
<p>The L2CAP connection handle to the remote device. This handle is only valid for notifications that
     arrive over an established L2CAP connection.</p>
</dd>

### -field BtAddress

<dd>
<p>The Bluetooth address of the remote device.</p>
</dd>

### -field Parameters

<dd>
<dl>

### -field Connect

<dd>
<p>The structure that contains parameters for the 
      <b>IndicationRemoteConnect</b> callback function.</p>
<dl>

### -field Request

<dd>
<p>The structure that contains the parameters for a connection request.</p>
<dl>

### -field PSM

<dd>
<p>The Protocol/Service Multiplexer (PSM) that is passed to the calling function when the 
        <b>IndicationRemoteConnectINDICATION_CODE</b> value is specified in the callback function's 
        <i>Indication</i> parameter.</p>
</dd>
</dl>
</dd>
</dl>
</dd>

### -field ConfigRequest

<dd>
<p>The structure that contains parameters for the 
      <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.</p>
<dl>

### -field CurrentParams

<dd>
<p>A 
       <a href="..\bthddi\ns-bthddi--channel-config-parameters.md">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.</p>
</dd>

### -field RequestedParams

<dd>
<p>A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.</p>
</dd>

### -field ResponseParams

<dd>
<p>A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that the profile driver
       responds to the configuration request with.</p>
</dd>

### -field Response

<dd>
<p>A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       </p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_SUCCESS</p>
</td>
<td>
<p>The configuration request was successful.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_DISCONNECT</p>
</td>
<td>
<p>The configuration request failed because the L2CAP connection was disconnected.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_INVALID_PARAMETER</p>
</td>
<td>
<p>The configuration request failed because an invalid parameter was passed to the profile
          driver.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_REJECT</p>
</td>
<td>
<p>The profile driver rejected the configuration request.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_UNKNOWN_OPTION</p>
</td>
<td>
<p>The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>
</dd>

### -field ConfigResponse

<dd>
<p>The structure that contains parameters for the 
      <b>IndicationRemoteConfigResponseINDICATION_CODE</b> value.</p>
<dl>

### -field CurrentParams

<dd>
<p>A 
       <a href="..\bthddi\ns-bthddi--channel-config-parameters.md">
       CHANNEL_CONFIG_PARAMETERS</a> structure that contains the parameters for the current channel. This
       value is only valid if the channel was previously open and is now in the process of being configured.
       This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.</p>
</dd>

### -field RequestedParams

<dd>
<p>A CHANNEL_CONFIG_PARAMETERS structure that contains the parameters that are passed from the
       remote host for configuration requests. This member is used when the callback function specifies the 
       <b>IndicationRemoteConfigRequestINDICATION_CODE</b> value.</p>
</dd>

### -field RejectedParams

<dd>
<p>A CHANNEL_CONFIG_PARAMETERS structure that contains the configuration parameter settings that
       were rejected by the remote device.</p>
</dd>

### -field UnknownTypes

<dd>
<p>An array of types that were not recognized by the responding device.</p>
</dd>

### -field NumUnknownTypes

<dd>
<p>The number of unrecognized types in the 
       <b>UnknownTypes</b> member.</p>
</dd>

### -field NewRequestParams

<dd>
<p>A CHANNEL_CONFIG_PARAMETERS structure that contains the parameter settings for the callback
       function to resubmit after the response has returned from the remote device.</p>
</dd>

### -field Response

<dd>
<p>A flag that indicates the status of the configuration request. Valid flag values are listed in
       the following table.
       </p>
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_SUCCESS</p>
</td>
<td>
<p>The configuration request was successful.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_DISCONNECT</p>
</td>
<td>
<p>The configuration request failed because the L2CAP connection was disconnected.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_INVALID_PARAMETER</p>
</td>
<td>
<p>The configuration request failed because an invalid parameter was passed to the profile
          driver.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_REJECT</p>
</td>
<td>
<p>The profile driver rejected the configuration request.</p>
</td>
</tr>
<tr>
<td>
<p>CONFIG_STATUS_UNKNOWN_OPTION</p>
</td>
<td>
<p>The configuration request failed because one of the specified configuration options was not
          recognized by the profile driver.</p>
</td>
</tr>
</table>
<p> </p>
</dd>
</dl>
</dd>

### -field FreeExtraOptions

<dd>
<p>The structure that contains parameters for the 
      <b>IndicationFreeExtraOptionsINDICATION_CODE</b> value.</p>
<dl>

### -field NumExtraOptions

<dd>
<p>The number of extra options contained in the 
       <b>ExtraOptions</b> member.</p>
</dd>

### -field ExtraOptions

<dd>
<p>The number of extra options contained in the 
       <b>ExtraOptions</b> member.</p>
</dd>
</dl>
</dd>

### -field Disconnect

<dd>
<p>The structure that contains the parameters for the 
      <b>IndicationRemoteDisconnectINDICATION_CODE</b> value.</p>
<dl>

### -field Reason

<dd>
<p>An 
       <a href="..\bthddi\ne-bthddi--l2cap-disconnect-reason.md">L2CAP_DISCONNECT_REASON</a> value that
       indicates why the L2CAP connection to the remote device was terminated.</p>
</dd>

### -field CloseNow

<dd>
<p>A Boolean value that a profile driver uses to notify the Bluetooth driver stack to close the
       L2CAP connection. Set this member to <b>TRUE</b> to notify the Bluetooth driver stack to close the
       connection. Otherwise, set it to <b>FALSE</b> to keep the connection open.</p>
</dd>
</dl>
</dd>

### -field RecvPacket

<dd>
<p>The structure that contains the parameters for the 
      <b>IndicationRecvPacketINDICATION_CODE</b> value.</p>
<dl>

### -field PacketLength

<dd>
<p>The size, in bytes, of the packet that the callback function sent over the L2CAP
       connection.</p>
</dd>

### -field TotalQueueLength

<dd>
<p>The number of packets to be processed over the L2CAP connection.</p>
</dd>
</dl>
</dd>
</dl>
</dd>
</dl>

## -remarks
<p>A profile driver's 
    <a href="..\bthddi\nc-bthddi-pfnbthport-indication-callback.md">L2CAP Callback Function</a> should
    process this structure differently depending upon the value that the Bluetooth driver stack passes in the
    
    <i>Indication</i> parameter of the callback function.</p>

<p>When the Bluetooth driver stack passes 
    <b>IndicationRemoteConnect</b>, the callback function should use the 
    <b>Connect</b> member of the 
    <b>Parameters</b> union.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Versions: Supported in Windows Vista, and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\bthddi\nc-bthddi-pfnbthport-indication-callback.md">L2CAP Callback Function</a>
</dt>
<dt>
<a href="..\bthddi\ns-bthddi--channel-config-parameters.md">CHANNEL_CONFIG_PARAMETERS</a>
</dt>
<dt>
<a href="..\bthddi\ns-bthddi--l2cap-config-option.md">L2CAP_CONFIG_OPTION</a>
</dt>
<dt>
<a href="..\bthddi\ne-bthddi--l2cap-disconnect-reason.md">L2CAP_DISCONNECT_REASON</a>
</dt>
<dt>
<a href="..\bthddi\ne-bthddi--indication-code.md">INDICATION_CODE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [bltooth\bltooth]:%20INDICATION_PARAMETERS structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>