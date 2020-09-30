---
title: Icons for WSD devices may show up incorrectly as a different class under Devices and Printers
description: This article describes an issue with Web Services for Devices, and includes an automated FixIt solution.
ms.date: 09/21/2020
author: Deland-Han
ms.author: delhan 
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-client
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: Devices and Drivers
ms.technology: Deployment
---
# Icons for WSD devices may show up incorrectly as a different class under Devices and Printers

This article provides a resolution for the issue that icons for WSD devices may show up incorrectly.

_Original product version:_ &nbsp; Windows 7 Service Pack 1  
_Original KB number:_ &nbsp; 2403006

## Symptoms

A Web Services for Devices (WSD) device may show the incorrect icon when viewed in Devices and Printers. For example, a WSD printer may show up with a Server icon and appear under Devices instead of showing a printer icon under Printers and Faxes.

## Cause

This issue is caused by an incorrect Device Stage  package released by Microsoft and available between June 8 and June 22, 2010.

## Resolution

To resolve this problem, clear out the Device Stage Metadata Store and download new packages. To do this, follow these steps:

1. Open an elevated (Administrator) Command Prompt.

2. Type del /s "%systemdrive%\users\%username%\AppData\Local\Microsoft\Device Metadata\\\*.*"  and press Enter.

3. Type Y  to the Are you sure (Y/N)  prompt and press Enter.

4. You may need to type Y  to confirm several more deletions, depending on the number of Device Stage  packages currently on your computer. (all of them will be freshly downloaded by Windows)

These steps will delete the cache contents containing the incorrect package and prompt Windows 7 to redownload the appropriate packages with the correct Device Metadata.