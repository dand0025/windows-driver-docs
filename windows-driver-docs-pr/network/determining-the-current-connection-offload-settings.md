---
title: Determining the Current Connection Offload Settings
description: Determining the Current Connection Offload Settings
ms.assetid: aca377ae-c56b-4f84-8165-4b084bfa9938
keywords: ["connection offload WDK TCP/IP transport , current settings", "current connection offload settings WDK TCP/IP offload"]
---

# Determining the Current Connection Offload Settings


## <a href="" id="ddk-determining-the-current-connection-offload-settings-ng"></a>


Protocol drivers can obtain the connection offload services with an object identifier (OID) request.

To obtain the current connection offload settings of a network interface card (NIC), protocol drivers can query the [OID\_TCP\_CONNECTION\_OFFLOAD\_PARAMETERS](https://msdn.microsoft.com/library/windows/hardware/ff569804) OID.

 

 





