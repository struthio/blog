---
layout: post
title:  "Enable Power Management tab on AX211 card"
date:   2023-02-05 22:16:57 +0100
categories: M16 Windows Power ax211
---
By default power management tab on Windows 11 is disabled for AX211 Card. To enable It You have to edit Registry:

In registry go to: 
	HKLM\System\CurrentControlSet\Control\Power

Add PlatformAoAcOverride entry as DWORD type with value set to 0
