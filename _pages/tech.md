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
    - [Python](https://www.python.org)
    - [Matplotlib: Visualization with Python](https://matplotlib.org)
    - [NumPy: The fundamental package for scientific computing with Python](https://numpy.org)
    - [SciPy: Scientific Library for Python](https://pypi.org/project/scipy/)
    - [SymPy: Python library for symbolic mathematics](https://www.sympy.org/en/index.html)
    - [Tabulate: Pretty-print tabular data in Python](https://pypi.org/project/tabulate/)
    - [Ahkab: SPICE-like electronic circuit simulator written in Python](https://github.com/ahkab/ahkab)
    - [Schemdraw: A Python package for producing high-quality electrical circuit schematic diagrams](https://pypi.org/project/schemdraw/)  
      
      Python packages can also be installed via `pip3` on Python3 (or `pip` for Python2), e.g.  
      `pip3 install *package name*`  
      
- Wolfram — [Maths and Notations](https://reference.wolfram.com/language/tutorial/MathematicalAndOtherNotation.html#41) 
- Shell Scripting — [developer.apple.com](https://developer.apple.com/library/archive/documentation/OpenSource/Conceptual/ShellScripting/shell_scripts/shell_scripts.html)  
  
  
## Tech Troubleshooting ##

### Mac: Problem with the keyboard volume controller ###
Error/Problem: Volume controller stops working etc.  
Solution: If quitting and restarting *coreaudiod* doesn't work, use the following command in the Terminal.  
  
`` sudo kill -9 `ps ax | grep 'coreaudiod' | grep -v grep | awk '{print $1}'` ``  
  

### LaTeX: *biber* gave return code 2 ###
Error/Problem: For whatever reason, *biber* or *biblatex* stopped working with the error "... gave return code 2..."  
Solution: Just reset the *biber* cache via the following command in Terminal (Mac).  
  
`rm -Rf "$(biber --cache)"`  
  
  
### Ahkab: Problem producing plots in Python3 ###
Error/Problem: Plotting graphs using ahkab in Python3 produces the error "module 'pylab' has no attribute 'hold'".  
Solution: 'Hold' for plots is enabled by default on Python3.  
1. First, find out the directory of which *ahkab* was installed using `pip3 list -v`.
2. In the *ahkab* folder, open *plotting.py*. Then, look for the lines containing `pylab.hold(True)` and `pylab.hold(False)`. Either remove them completely or comment them out.  
4. An alternative solution is to use *ahkab* with Python2. However, this is not encouraged due to the deprecation of Python2 and also the lack of support with most transitting towards Python3.  
 
 
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


### Startup Key Combos ###

### Macs with Apple Silicon ###
1. During startup after restarting your Mac or from a fresh boot, **continue to press and hold on the power button**.
2. Release power button when the startup options screen appears.
3. Window with startup functions similar to Intel-based Macs below will carry you through.  

#### Intel-based Macs ####
* **Command (⌘)-R**: Boot from the built-in macOS Recovery system.
* **Option-Command-R** or **Shift-Option-Command-R**: Boot from macOS Recovery over the internet.
* **Option (⌥) or Alt**: Boot to Startup Manager. You can choose options for startup disks via here.
* **Option-Command-P-R**: Reset NVRAM or PRAM. This can be used to reset peripherals and devices that have been acting weird, e.g. mouse, keyboard, etc.
* **Shift (⇧)**: Boot in safe mode.
* **D**: Boot to the Apple Diagnostics utility (use **Option-D** to boot to ADU with internet).
* **Command-V**: Boot in verbose mode.

