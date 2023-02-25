---
layout: post
title:  "Start Eagle CAD on Ubuntu"
date:   2023-02-25 21:21:21 +0100
categories: ubuntu eagle cad
---
Eagle CAD in newest version 9.6.2 didn't wanted to start on my PC. When staring all windows became black and I couldn't see anything.
Solition to problem was to enable software rendering:

LIBGL_ALWAYS_SOFTWARE=1 ./eagle
