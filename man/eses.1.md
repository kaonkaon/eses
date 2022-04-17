% ESES(1) eses 
% WTechNinja
% April 2022

# NAME
eses - Screenshot scripts with QR Scanner feature

# SYNOPSIS
**eses** [OPTION]

	
# DESCRIPTION
Basic screenshot script with QR Scanner feature (yes i wrote this twice). Good for making a keybind for screenshots (you can use another decent apps/scripts, really)
In the **--select-cp** mode, if there's a QR Code detected in the picture, it will try to scan it. If it fails, it will leave the screenshot copied on the clipboard, if it succeeds it will prompt to ask if you want the QR Code result on your clipboard.
Has four different modes, selectable via options.

# OPTIONS
**--whole**
: Screenshot whole screen (without cursor) and save it as a file in your desired folders (set it yourself by changing the scripts)

**--select**
: Screenshot selected area / selected window, and save it as a file

**--whole_cp**
: Screenshot whole screen (without cursor) and put it on clipboard without saving (save your precious Kb in your HDD/SSD)

**--select_cp**
: Screenshot selected area / selected window, and put it on clipboard, then run QR code magic. 

# EXAMPLES
**eses --select_cp**
: Screenshot selected area to clipboard, then run QR code magic.

**eses --whole**
: Screenshot whole screen, and save as file.

# BUGS
https://github.com/kaonkaon/eses

