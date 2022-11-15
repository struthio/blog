---
layout: post
title:  "Generate battery health raport in windows"
date:   2022-11-15 23:18:57 +0100
categories: M16 Windows
---
In order to check Your laptop battery capacity, You can generate battery report in Windows.

In PowerShell (Admin), run:

	powercfg /batteryreport /output "<Location>\raport.html"

Where <location> is path on disk where raport should be created.
