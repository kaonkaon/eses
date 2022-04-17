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
			* if its success, user will be prompted to either copy the image or scanned result
			 ![Dialog](https://github.com/kaonkaon/eses/blob/main/me%20when%20dialog.png?raw=true)
			 
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

### Install
just copy it to executable path and make it executable and boom 

##### Using WGET (on /usr/local/bin)
```
wget https://raw.githubusercontent.com/kaonkaon/eses/main/eses
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
##### Using Clone (on /usr/local/bin)
```
cd /tmp
git clone https://github.com/kaonkaon/eses.git
cd eses
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
##### Rewrite the thing (when Copy Paste is bloat)
```
open your favorite text editor
write the entire thing
save
put it in random folder
```

#### Building the man page
`eses.1.md` is just a markdown file, feel free to edit it to your liking and then, while in the `man` folder run;
```
pandoc eses.1.md -s -t man -o eses.1	
gzip eses.1 -c > eses.1.gz
```
then the generated `eses.1.gz` file can be installed in `/usr/local/man/man1`  
After that, you can use `man eses` to view the man page.


## Contribute
please contribute something, even adding comment is appreciated
