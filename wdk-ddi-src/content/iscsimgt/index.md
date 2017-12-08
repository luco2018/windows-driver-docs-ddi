# Iscsimgt.h header


This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Iscsimgt.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [ISCSI_ConnectionStaticInfo structure](ns-iscsimgt--iscsi-connectionstaticinfo.md) | The ISCSI_ConnectionStaticInfo structure contains information about the characteristics of an established connection. |
| [ISCSI_Path structure](ns-iscsimgt--iscsi-path.md) | The ISCSI_Path structure contains information about a connection of the iSCSI portal. |
| [ISCSI_PortalInfo structure](ns-iscsimgt--iscsi-portalinfo.md) | The ISCSI_PortalInfo structure contains information about an iSCSI portal. |
| [ISCSI_RedirectPortalInfo structure](ns-iscsimgt--iscsi-redirectportalinfo.md) | This ISCSI_RedirectPortalInfo structure contains information about a collection of iSCSI portals that can be used during portal hopping or portal redirect operations. |
| [ISCSI_RedirectSessionInfo structure](ns-iscsimgt--iscsi-redirectsessioninfo.md) | This ISCSI_RedirectSessionInfo structure contains information about an iSCSI session and its portal information resulted from iSCSI target redirection. |
| [ISCSI_SessionStaticInfo structure](ns-iscsimgt--iscsi-sessionstaticinfo.md) | The ISCSI_SessionStaticInfo structure provides information about the characteristics of an iSCSI session. |
| [ISCSI_Supported_LB_Policies structure](ns-iscsimgt--iscsi-supported-lb-policies.md) | The ISCSI_Supported_LB_Policies structure contains information about load balancing policies for multiple connections per session (MCS). |
| [MSiSCSI_Eventlog structure](ns-iscsimgt--msiscsi-eventlog.md) | This MSiSCSI_EventLog method is used to log any messages to the event log. |
| [MSiSCSI_HBAInformation structure](ns-iscsimgt--msiscsi-hbainformation.md) | The MSiSCSI_HBAInformation structure is used by storage miniport drivers to report information about the host bus adapters (HBAs) that they manage to the iSCSI initiator service. |
| [MSiSCSI_HBASessionConfig structure](ns-iscsimgt--msiscsi-hbasessionconfig.md) | The MSiSCSI_HBASessionConfig structure contains the default logon characteristics that a particular instance of a storage miniport driver uses to create a logon session with a target device. |
| [MSiSCSI_InitiatorInstanceFailureEvent structure](ns-iscsimgt--msiscsi-initiatorinstancefailureevent.md) | The MSiSCSI_InitiatorInstanceFailureEvent structure is used to report an event when an initiator instance failure occurs. |
| [MSiSCSI_InitiatorNodeFailureEvent structure](ns-iscsimgt--msiscsi-initiatornodefailureevent.md) | The MSiSCSI_InitiatorNodeFailureEvent structure is used to report an event when a node failure occurs. |
| [MSiSCSI_InitiatorSessionInfo structure](ns-iscsimgt--msiscsi-initiatorsessioninfo.md) | The MSiSCSI_InitiatorSessionInfo structure contains information about a collection of sessions that belong to the indicated HBA initiator. |
| [MSiSCSI_PortalInfoClass structure](ns-iscsimgt--msiscsi-portalinfoclass.md) | The MSiSCSI_PortalInfoClass structure contains information about a collection of iSCSI portals. |
| [MSiSCSI_QueryLBPolicy structure](ns-iscsimgt--msiscsi-querylbpolicy.md) | This MSiSCSI_QueryLBPolicy method returns the MCS load balancing policy for each information if any that has been set across different iSCSI session. |
| [MSiSCSI_RedirectPortalInfoClass structure](ns-iscsimgt--msiscsi-redirectportalinfoclass.md) | The MSiSCSI_RedirectPortalInfoClass structure contains information about a collection of sessions for an adapter ID. It also contains the portal redirection information for each of the sessions. |
| [PingIPAddress_IN structure](ns-iscsimgt--pingipaddress-in.md) | The PingIPAddress_IN structure holds the input data for the PingIPAddress method. |
| [PingIPAddress_OUT structure](ns-iscsimgt--pingipaddress-out.md) | The PingIPAddress_OUT structure holds the output data for the PingIPAddress method. |
| [SetLoadBalancePolicy_IN structure](ns-iscsimgt--setloadbalancepolicy-in.md) | The SetLoadBalancePolicy_IN structure holds the input data for the SetLoadBalance method. |
| [SetLoadBalancePolicy_OUT structure](ns-iscsimgt--setloadbalancepolicy-out.md) | The SetLoadBalancePolicy_OUT structure holds the output data for the SetLoadBalance method. |