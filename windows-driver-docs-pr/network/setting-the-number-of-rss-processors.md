---
title: Setting the Number of RSS Processors
description: Setting the Number of RSS Processors
ms.assetid: c13db4a1-e345-4368-9bcd-afbd2fd8db7a
keywords: ["processors WDK RSS", "CPU configuration WDK RSS"]
---

# Setting the Number of RSS Processors


## <a href="" id="ddk-setting-the-number-of-rss-processors-ng"></a>


Administrators should set the number of receive side scaling (RSS) processors to help the overall performance of a computer. Concurrent deferred procedure calls (DPCs) that are running on multiple CPUs enable distributed receive processing and remove the CPU bottleneck (for example, in high-speed NICs). However, multiple DPCs do create additional overhead. The interrupt and DPC processing overhead increases as more processors are used for RSS. Therefore, when RSS is active, the total CPU utilization across all CPUs increases. An administrator should select the number of CPUs that are used for RSS to avoid a situation where using RSS leaves less processing power for applications to use and does not improve network throughput.

In Microsoft Windows Server 2003 with the Scalable Networking Pack, administrators can set the maximum number of RSS CPUs with the **MaxNumRssCpus** registry keyword in **HKEY\_LOCAL\_MACHINE\\\\SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Parameters**. The **MaxNumRssCpus** value is a DWORD type and, if it is not present, NDIS uses the default value of 4.

In Windows Server 2008, administrators can set the maximum number of RSS CPUs with the **MaxNumRssCpus** registry keyword in **HKEY\_LOCAL\_MACHINE\\\\SYSTEM\\CurrentControlSet\\Services\\Ndis\\Parameters**. The **MaxNumRssCpus** value is a DWORD type and, if it is not present, NDIS uses the default value of 4.

To avoid complicated cases (and unrealistic cases that are not implemented in actual hardware) where the number of available hardware receive queues is less than the number of RSS CPUs, administrators must not set the **MaxNumRssCpus** value to a value that is greater than 16.

**Note**  The actual number of CPUs that are used for RSS is also limited by the total number of core processors that remain after the RSS base CPU number has been configured. For example, if the administrator sets the maximum number of RSS CPUs on a quad-core computer system to 6, the networking driver stack uses, at most, 4 CPUs for RSS. If the administrator also sets the RSS base CPU number to 1, the networking driver stack uses at most 3 CPUs (CPU numbers 1, 2, and 3).

 

The number of CPUs that the computer uses for RSS is static and does not change at run time. Therefore, any changes to the **MaxNumRssCpus** registry value require a restart to take effect.

 

 





