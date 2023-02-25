---
layout: post
title:  "Disable core parking"
date:   2023-02-06 22:02:23 +0100
categories: M16 Windows Power cpu
---
To disable Core Parking, You need to edit Windows registry:
In HKLM\SYSTEM\ControlSet001\Control\Power\PowerSettings\ search for a key ending with dec35c318583

Then click on Attribute key and change value from 2 to 0.

Now in Power Profile configuration You should have option "Processor performance core parking min cores". Setting to value 100% prevents core parking.
