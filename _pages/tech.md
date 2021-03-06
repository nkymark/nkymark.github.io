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

If you ever come across a printing problem with the error message “Hold On Authentication”, you can reset the password to the network printer via the following command in Terminal:

`sudo lpadmin -p printername -o auth-info-required=username,password`


### Fixing Hardware Acting Crazy on A Mac, i.e. Trackpad not working, screen acting weird, etc. ###
These steps can be used on most modern Macs. I suggest that you try the PRAM Reset first. If problem still persists, you can then attempt the SMC Reset. 


**PRAM Reset**
1. Shut down your Mac.
2. Turn on your Mac. 
3. Press and hold the keys **Command + Option + P + R simultaneously before the gray screen appears**. Else, restart the whole process.
4. Wait for your Mac to restart itself again and that you hear the startup chime.
5. You can let go of the keys now. Your Mac will start as it normally does.


**SMC Reset**
1. Shut down your Mac.
2. a) For MacBooks with removable batteries
    - Disconnect the MagSafe cable.
    - Remove the battery.
    - Press the Power key for 5 seconds and then let go. 
    - Put back the battery and reattach the MagSafe cable.

   b) For MacBooks without removable batteries
    - Keep the MagSafe cable attached.
    - Press (on the left hand side of the keyboard) the Shift + Control + Option and the Power keys simultaneously. 
    - Let go of all keys at the same time.

   c) For iMacs and other non-laptop based Macs
    - Disconnect the power cable.
    - Press the Power key for 5 seconds and then let go. 
    - Reattach the power cable.

3. Turn your Mac back on.
