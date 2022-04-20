# eses-beta
Screenshot script with QR Scanner feature (Forked from [u/LithiumFrost](https://www.reddit.com/r/unixporn/comments/p0md2y/oc_scan_a_qr_code_with_a_keyboard_shortcut/) [Codes](https://github.com/jayden-chan/dotfiles/blob/7f4ab0257604a52b3f5befe73cf21a5f95a19f54/scripts/screenshot.sh#L13)) (beta version)

<h2><span style="color:red">!! BETA VERSION !!</span></h2>
this is beta version, something is (maybe) broken and unstable and questionable

this is for test purpose, please be careful

---
### Name Meaning
How you pronounce "SS"? yeah. added `-beta` for beta version.

### Description
Basic screenshot script with QR Scanner feature (yes i wrote this twice). Good for making a keybind for screenshots (you can use another decent apps/scripts, really)  
It should be noted that the cursor isn't included in screenshots.

#### milestones
* added user config support (already merged to main)
* added wayland support (big thanks to [WTechNinja](https://github.com/WTechNinja) ([jump to his repo](https://github.com/WTechNinja/eses/tree/eses-w)) ( the wayland support belongs to WTechNinja )

### Function
* --whole
	* Screenshot whole screen and save it as a file in your desired folders (set it yourself by changing the config)
* --select
	* Screenshot selected area / selected window, and save it as a file
* --whole_cp
	* Screenshot whole screen and put it on clipboard without saving (save the precious Kb on your HDD/SSD)
* --select_cp
	* Screenshot selected area / selected window, and put it on clipboard
		* if there's a QR Code detected in the pictures, it will try to scan it
			* if it fails, it will leave the screenshot copied on the clipboard
			* if it succeeds, user will be prompted to copy either the screenshot or scanned result
			 ![Dialog](https://github.com/kaonkaon/eses/blob/main/me%20when%20dialog.png?raw=true)
			 
### Configuration
All of the default configuration is in the beginning of the eses script with plenty of comments, and it will likely change. As of writing this, the default config is:

```
# Notification title when a screenshot is saved to disk, or copied to clipboard
succ_noTit="Kasha!"

# Notification text when a screenshot is captured, and saved to disk
succ_noTex="Screenshot saved!"

# Notification text when a screenshot is captured, and copied to clipboard
succ_noTex_cp="Screenshot copied to clipboard!"

# Notification title when a QR Code is scanned and copied to clipboard
succ_noTit_sccop="QR Code scan result"

# Prompt dialog title when qr code scanned
dia_tit="Prompt"

# Prompt dialog text when qr code scanned
dia_tex="QR Code detected, and sucessfully scanned.\n Do you want to copy the scan result instead?"

# Prompt dialog copy image button
dia_imgcop_butt="Copy image"

# Prompt dialog copy scan result button
dia_sccop_butt="Copy scan result"

# Screenshot save dir
sv_dir="/home/$USER/Pictures/"

# Screenshot file name
sv_name="$(date)"
```

### Dependencies
> General
```
zenity
imagemagick
notify-send
zbarimg
```

> Xorg
```
maim
xclip
```

> Wayland
```
grim
wl-clipboard
```

### Install
just copy it to executable path and make it executable and boom 

##### Using Clone (on /usr/local/bin)
```
cd /tmp
git clone https://github.com/kaonkaon/eses.git
cd eses
git checkout beta
sudo mv eses-beta /usr/local/bin/
chmod +x /usr/local/bin/eses-beta
```
##### Using WGET (on /usr/local/bin)
> man page not included, download it yourself
```
wget https://raw.githubusercontent.com/kaonkaon/eses/beta/eses-beta
sudo mv eses-beta /usr/local/bin/
chmod +x /usr/local/bin/eses-beta
```
##### Rewrite the thing (when Copy Paste is bloat)
```
open your favorite text editor
write the entire thing
save
put it in random folder
```

#### Building the man page
> dependencies: pandoc, gzip

`eses.1.md` is just a markdown file, feel free to edit it to your liking and then, while in the `man` folder run;
```
pandoc eses.1.md -s -t man -o eses.1	
gzip eses.1 -c > eses.1.gz
```
then the generated `eses.1.gz` file can be installed in `/usr/local/man/man1`  
```
# Make /usr/local/man/man1 if it doesn't already exist
sudo mkdir -p /usr/local/man/man1

sudo mv eses.1.gz /usr/local/man/man1/
sudo mandb
```
After that, you can use `man eses` to view the man page.

#### Config File
upon first run, the config file will be generated under `/home/$USER/.config/eses-beta/`

script will automatically generate the directory and config file with default configuration inside if theres no config directory and/or config file. no worry i get you 


## Contribute
please contribute something, even adding comment is appreciated.
