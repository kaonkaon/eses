# eses
Screenshot script with QR Scanner feature (Forked from [u/LithiumFrost](https://www.reddit.com/r/unixporn/comments/p0md2y/oc_scan_a_qr_code_with_a_keyboard_shortcut/) [Codes](https://github.com/jayden-chan/dotfiles/blob/7f4ab0257604a52b3f5befe73cf21a5f95a19f54/scripts/screenshot.sh#L13))

### Name Meaning
How you pronounce "SS"? yeah.

### Description
Basic screenshot script with QR Scanner feature (yes i wrote this twice). Good for making a keybind for screenshots (you can use another decent apps/scripts, really)  
It should be noted that the cursor isn't included in screenshots.

#### milestones
* added user config support 
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
* --help
	* Show help page with information on basic usage			
 
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

You can configure these settings by creating "config" files under ~/.config/eses/ (it should create the config files automatically)

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

### Install stable version
just copy it to executable path and make it executable and boom 

##### Using git clone (on /usr/local/bin)
```
cd /tmp
git clone https://github.com/kaonkaon/eses.git
cd eses
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
##### Using WGET (on /usr/local/bin)
> man page not included, download it yourself
```
wget https://raw.githubusercontent.com/kaonkaon/eses/main/eses
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
### Install specific branch version
> This is only useful for testing new features, we recommend you stick to the stable version  

go to whichever branch you want, download `eses` and make it executable and put it somewhere
##### Using git clone (on /usr/local/bin)
Replace `<placeholder>` with the name of the branch you want, like `beta` or `config`
```
cd /tmp
git clone https://github.com/kaonkaon/eses.git
cd eses
git checkout <placeholder>
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
##### Using WGET (on /usr/local/bin)
> man page not included, download it yourself  

Replace `<placeholder>` with the name of the branch you want, like `beta` or `config`
```
wget https://raw.githubusercontent.com/kaonkaon/eses/<placeholder>/eses
sudo mv eses /usr/local/bin/
chmod +x /usr/local/bin/eses
```
##### Rewrite the thing (when Copy and Paste are bloat. Works for any branch)
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
upon first run, the config file will be generated under `/home/$USER/.config/eses/`

the script will automatically generate the directory and config file with default configuration inside if there's no config directory and/or config file. no worry i get you 


## Contribute
please contribute something, even adding a comment is appreciated.
