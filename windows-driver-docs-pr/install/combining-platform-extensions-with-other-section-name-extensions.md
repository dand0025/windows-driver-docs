---
title: Combining Platform Extensions with Other Section Name Extensions
description: Combining Platform Extensions with Other Section Name Extensions
ms.assetid: ca82ba0f-0d65-47ca-826a-4f78435b1442
keywords: ["INF files WDK device installations , platform extensions", "platform extensions WDK INF files", "extensions WDK INF platform", "combining platform extensions WDK INF files", "install-section-name WDK INF files", "decorated INF WDK", "operating systems WDK"]
---

# Combining Platform Extensions with Other Section Name Extensions


An INF file that contains INF *DDInstall* sections with platform extensions can also contain additional per-device sections, such as the required *DDInstall***.Services** and optional *DDInstall***.HW**, *DDInstall***.CoInstallers**, *DDInstall***.LogConfigOverride**, and *DDInstall***.Interfaces** sections. In cross-operating system and cross-platform INF files, you should specify the appropriate platform extension immediately after the INF-writer-defined section name (for example, *install-section-name***.ntx86.HW**).

If a cross-operating system INF file contains decorated *install-section-name***.nt**, *install-section-name***.ntx86**, *install-section-name***.ntia64**, or *install-section-name***.ntamd64** sections, it must also have additional parallel decorated and undecorated per-device sections. That is, if the INF file has both *install-section-name* and *install-section-name***.nt** sections and it has a *DDInstall*.**HW** section, it must also have a parallel *install-section-name***.nt.HW** section (if the device or driver requires a **.HW** section for Windows 2000 and later versions of Windows).

The topics in the [INF File Sections and Directives](inf-file-sections-and-directives.md) section show the **nt***xxx***.HW** extensions as part of the formal syntax statements in the appropriate section references, such as in the following example:

**\[***install-section-name***.HW\]** |
**\[***install-section-name***.nt.HW\]** |
**\[***install-section-name***.ntx86.HW\]** |
**\[***install-section-name***.ntia64.HW\]** |
**\[***install-section-name***.ntamd64.HW\]**
Such a formal syntax statement indicates that these extensions are valid alternatives to the basic section. This type of statement does *not* indicate that any INF file that has an *install-section-name***.nt.HW** section must also include every other platform-specific *install-section-name***.nt***xxx***.HW** section. You can use any subset of these extensions to specify the decorated sections that are required for a particular cross-platform installation.

INF files that contain *install-section-name* platform extensions can also include platform extensions with their [**INF SourceDisksNames section**](inf-sourcedisksnames-section.md) and [**INF SourceDisksFiles section**](inf-sourcedisksfiles-section.md) entries, to specify installation file locations in a platform-specific manner.

 

 





