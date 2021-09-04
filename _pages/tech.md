---
permalink: /tech/
layout: single
title: Tech Stuff
---

# Some “Note to Self” Research and Tech (mostly for Mac) Stuffs #

## Some Useful Links ##
- Research Publications
    - [ISI Journals Impact Factor and Citation Report](https://jcr.clarivate.com)
    - [ISI Journals Finder and Matcher](https://mjl.clarivate.com/home)
    - [IEEE Publication Recommender](https://publication-recommender.ieee.org/home)
    - [Elsevier Journal Finder](https://journalfinder.elsevier.com)
    - [Springer Nature Journal Suggester](https://journalsuggester.springer.com)
    - [Wiley Journal Finder](https://journalfinder.wiley.com/search?type=match)
    - [TechRxiv: IEEE Preprint Server](https://www.techrxiv.org)
    - [IEEE Publication Policies](https://journals.ieeeauthorcenter.ieee.org/become-an-ieee-journal-author/publishing-ethics/guidelines-and-policies/post-publication-policies/)
    - [Sherpa REF Checker](https://ref.sherpa.ac.uk)
- LaTeX
    - [MacTex (TeX for Mac)](https://www.tug.org/mactex/)
    - [MikTex (TeX for Mac, Linux, and Windows)](https://miktex.org)
    - [siunitx: A comprehensive (si) units package](https://texdoc.org/serve/siunitx.pdf/0)
    - [Tables Generator](https://www.tablesgenerator.com)
    - [LaTeX Graphics using TikZ](https://www.overleaf.com/learn/latex/LaTeX_Graphics_using_TikZ:_A_Tutorial_for_Beginners_(Part_1)—Basic_Drawing)
    - [Typesets block diagrams for control theory (with TikZ)](https://www.ctan.org/tex-archive/graphics/pgf/contrib/blox)
- Python
    - [Matplotlib: Visualization with Python](https://matplotlib.org)
    - [Ahkab: SPICE-like electronic circuit simulator written in Python](https://github.com/ahkab/ahkab)
    - [Schemdraw: A Python package for producing high-quality electrical circuit schematic diagrams](https://pypi.org/project/schemdraw/)
- Wolfram — [Maths and Notations](https://reference.wolfram.com/language/tutorial/MathematicalAndOtherNotation.html#41) 
- Shell Scripting — [developer.apple.com](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/shell_scripts/shell_scripts.html)  
  
  
## Tech Troubleshooting ##

### Mac: Problem with the keyboard volume controller ###
Error: Volume controller stops working etc.  
Solution: If quitting and restarting *coreaudiod* doesn't work, use the following command in the Terminal.  
  
`` sudo kill -9 `ps ax | grep 'coreaudiod' | grep -v grep | awk '{print $1}'` ``  
  

### LaTeX: *biber* gave return code 2 ###
Error/Problem: For whatever reason, *biber* or *biblatex* stopped working with the error "... gave return code 2..."  
Solution: Just reset the *biber* cache via the following command in Terminal (Mac).  
  
`rm -Rf "$(biber --cache)"`  
  
  
### Adding Windows Network Printer (Mac) ###
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


### Fixing Hardware Acting Crazy on a Mac, i.e. trackpad not working, screen acting weird, etc. ###
These steps can be used on most modern Macs. I suggest that you try the PRAM Reset first. If problem still persists, you can then attempt the SMC Reset. 


**PRAM Reset**
1. Shut down your Mac.
2. Turn on your Mac. 
3. Press and hold the keys **Command + Option + P + R simultaneously before the gray screen appears**. Else, restart the whole process.
4. Wait for your Mac to restart itself again and that you hear the startup chime.
5. You can let go of the keys now. Your Mac will start as it normally does.


**SMC Reset**
1. Shut down your Mac.
2. a) For MacBooks without removable batteries
    - Keep the MagSafe cable attached.
    - Press (on the left hand side of the keyboard) the Shift + Control + Option and the Power keys simultaneously. 
    - Let go of all keys at the same time.

   b) For iMacs and other non-laptop based Macs
    - Disconnect the power cable.
    - Press the Power key for 5 seconds and then let go. 
    - Reattach the power cable.

3. Turn your Mac back on.
