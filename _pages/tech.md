---
permalink: /tech/
layout: single
title: Tech Stuff
---

## Some “Note to Self” Tech Troubleshooting Steps ##


### Adding Windows Network Printer on A Mac ###
These steps apply for Mac OS X 10.11 El Capitan and later. Adjust accordingly for older versions.

1. **System Preferences -> Printers and Scanners**
2. Click on “**+** ” to add a new printer
3. Select “**Advanced**” from the top toolbar. If you don’t see it, right-click on the toolbar and select “**Customize Toolbar...**”. Drag the “**Advanced**” button into the toolbar.
4. Under “**Type**”, choose “**Windows printer via spools**”
5. Under “**Device**”, choose “**Another Device**”
6. Under “**URL**”, enter “`smb://printserver/printername`”
7. Enter the “**Name**” of your printer. “**Location**” is optional
8. “**Use**” the “**Generic PCL Driver**” for El Capitan and newer or “**General PCL 6 Driver**” for older versions of Mac OS X
9. Click on the “**Add**” button
10. You might be prompted to enter your login credentials. Choose “**Registered User**”, enter your login username “`admin\username`” followed by your password
11. Done. You should be able to use the printer now.

