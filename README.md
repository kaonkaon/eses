# eses
Screenshot scripts with QR Scanner feature (Forked from [u/LithiumFrost](https://www.reddit.com/r/unixporn/comments/p0md2y/oc_scan_a_qr_code_with_a_keyboard_shortcut/) [Codes](https://github.com/jayden-chan/dotfiles/blob/7f4ab0257604a52b3f5befe73cf21a5f95a19f54/scripts/screenshot.sh#L13))

### Name Meaning
How you pronounce "SS"? yeah.

### Description
Basic screenshot script with QR Scanner feature (yes i wrote this twice). Good for making a keybind for screenshots (you can use another decent apps/scripts, really)

### Function
* --whole
	* Screenshot whole screen (without cursor) and save it as a file in your desired folders (set it yourself by changing the scripts)
* --select
	* Screenshot selected area / selected window, and save it as a file
* --whole_cp
	* Screenshot whole screen (without cursor) and put it on clipboard without saving (save your precious Kb in your HDD/SSD)
* --select_cp
	* Screenshot selected area / selected window, and put it on clipboard
		* if theres QR Code detected in the pictures, it will try to scan the thing
			* if its fail, it will put the screenshotted result in to clipboard
			* if its success, user will be prompted to either copy the image or scanned result (insert image here)

### Configuration
All of the configuration are on the script with the description (should i describe them again in here?)

### Dependencies
```
* zenity
* maim
* imagemagick
* xclip
* zbarimg
* notify-send
```

WIP
