% ESES(1) eses 
% WTechNinja, kaonkaon
% April 2022

# NAME
eses - Screenshot script with QR Scanner feature

# SYNOPSIS
**eses** [OPTION]

	
# DESCRIPTION
Basic screenshot script with QR Scanner feature. Good for screenshot keybindings. It should be noted that the cursor isn't included in screenshots.
In the **--select-cp** mode, if there's a QR Code detected in the picture, it will try to scan it. If it fails, it will leave the screenshot copied on the clipboard, if it succeeds it will prompt to ask if you want the QR Code result on your clipboard.
Has four different modes, selectable via options.

# OPTIONS
**--whole**
: Screenshot whole screen and save it as a file in your desired folder (set it yourself by changing the config)

**--select**
: Screenshot selected area / selected window, and save it as a file

**--whole_cp**
: Screenshot whole screen and put it on clipboard without saving (save the precious Kb on your HDD/SSD)

**--select_cp**
: Screenshot selected area / selected window, and put it on clipboard, then run QR code magic. If a QR Code is detected in the screenshot, it will try to scan it. If it fails, it will leave the screenshot on the clipboard, but if it succeeds you will be prompted to copy either the image or the scanned result.

**--help**
: Show this help screen.
# EXAMPLES
**eses --select_cp**
: Screenshot selected area to clipboard, then run QR code magic.

**eses --whole**
: Screenshot whole screen, and save as file.

# CONFIGURATION
eses stores it's config file at /home/$USER/.config/eses/config.
If it doesn't exist, the script will automatically generate the directory and config file with default configuration.
The config file is commented with explanations of what all the variables do.

# BUGS
https://github.com/kaonkaon/eses

