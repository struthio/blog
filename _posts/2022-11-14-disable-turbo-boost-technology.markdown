---
layout: post
title:  "Disable Intel Turbo Boost Technology"
date:   2022-11-14 13:36:07 +0100
categories: M16 Windows
---
I work a lot in Silet profile. Turbo Boost causes CPU to jump to 5GHz and causes CPU to get so hot that fans have to kick in. CPU have a lot of power that even without Turbo Boost should be sufficient to me.
To keep up 'silent working' decision was made to disable Turbo Boost.

To disable Turbo Boost in Windows You need:

Enable hidden power menu. In Registry Editor:

1. HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\54533251-82be-4824-96c1-47b60b740d00\be337238-0d82-4146-a960-4f3749d470c7
2. Select Attributes
3. Modify value of "Attributes" from 1 to 2 ("0x00000002 (2)")

Modify power plan:

1. Go into Power Plan Options 
2. Open tab "Processor Performance Boost Mode" (Should appear after registry modification above)
3. Set it to Disable
4. Click Apply
5. (Optional)  Set max processor state to 100%
