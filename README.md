# Adobe Photoshop CC 2021 installer for Linux

![image](https://github.com/GordonZed/photoshop-22-linux/blob/main/screenshot.png)

Tested in Fedora 38+ as well as Pop!_OS (Ubuntu 22.04 LTS base). Let me know how it goes if you try it elsewhere.

## DISCLAIMER:
**Please use this software only if you have an active Photoshop subscription. I'm not responsible for any illegal use of this product.**

## Requirements
- An internet connection
- All **read** and **write** rights on your home folder and the folder of installation
- `git`
- `tar`
- `wget`
- `curl`
- `wine` >=6.22 (Avoid your distro's default \[usually outdated\] Wine package; add the distro-appropriate [WineHQ stable repo](https://wiki.winehq.org/Download))
- `gdown` - (To install: `pip install gdown`)
- Vulkan capable GPU or APU _(optional)_
- `appmenu-gtk-module` _(optional)_


## Installation guide:

>_**NOTE:** The total download size, is around 1.2GB_

>_**NOTE 2:** CLONE THIS REPO TO THE FOLDER YOU WANT TO KEEP PHOTOSHOP IN, EVERYTHING TO DO WITH THE PHTOTOSHOP INSTALLATION WILL HAPPEN THERE_

>_**NOTE 3:** THE ONLY FILE THAT WILL BE INSTALLED OUTSIDE THE CLONED FOLDER IS THE DESKTOP ENTRY: ~/.local/share/applications/photoshop.desktop_

>_**NOTE 4:** After installation, feel free to tidy up downloaded files (\[cloned_repo\]/installation_files/[downloaded_files].tar.xz). The installation will be in a new directory called "Ps-prefix", so that's the one directory (+files therein) you shouldn't touch._


Open your terminal and:

```bash
# Clone the repo

git clone https://github.com/GordonZed/photoshop-22-linux.git
cd photoshop-22-linux

# Run the main-menu file:

./main-menu.sh

# In the main menu, you will see these options:

"
-------------- Adobe Photoshop CC 2021 (v22)  installer main menu on Linux --------------

1) Install Photoshop CC 2021 (v22)            5) Configure Photoshop wine prefix (winecfg)
2) Uninstall Photoshop CC 2021 (v22)          6) Update desktop integration
3) Install Adobe Camera Raw Plugin            7) Exit
4) Install/Uninstall vdk3d proton

[Choose options 1-6 or 7 to exit]:
"
# To install photoshop select option "1"
# The installer will ask you if you want to install the Adobe Camera Raw Plugin (y/n)

"Would you like to install Adobe Camera Raw at the end?
(y/n): y"

# The installer will also ask you weather you want to install vdk3d proton,
# this utility allows you to use your GPU with wine (AMD GPUs might require some extra finesse; will try to add some info on that front when I have some free time).

"Would you like to install vdk3d proton?
(y/n): n"

# However, it can be a bit buggy. Therefore it's up to you weather to install it or not.
# You can always install it afterwards by selecting option "4":

"[Choose options 1-6 or 7 to exit]: 4

Would you like to install or uninstall vkd3d proton [i=install u=uninstall]: i"

# And after the installer does it's stuff...

"Vdk3d proton installed!"

# And to uninstall:

"[Choose options 1-6 or 7 to exit]: 4

Would you like to install or uninstall vkd3d proton [i=install u=uninstall]: u"

# And after the installer does it's stuff...

"Vdk3d proton uninstalled!"


# To uninstall Photoshop:

"[Choose options 1-6 or 7 to exit]: 2

Are you sure you want to uninstall Adobe Photoshop? (y/n): y

Photoshop uninstalled!"

# If you want to completely remove this installer, then delete the cloned folder after running the uninstaller.
```

### Install Files Fail to Download 

Sometimes, this error can show up:
```bash
Access denied with the following error:

 	Cannot retrieve the public link of the file. You may need to change
	the permission to 'Anyone with the link', or have had many accesses.

You may still be able to access the file from the browser:

	 https://drive.google.com/uc?id=...
```
If this occurs, open scripts/installer.sh in your favourite text editor (**omg!** that's my favourite text editor ***too!***) and grab the file ID from line 94 (random string in quote marks).

Insert the ID into this URL format: https://drive.google.com/file/d/***FILE_UUID_GOES_HERE***/view?usp=drive_link, and manually download `allredist.tar.xv` to the `installation_files` directory.

Now rinse and repeat using the file ID on line 100.

Re-run the script.

## Configure Photoshop:
<br>

**1-** Launch Photoshop and go to: `Edit -> preferences -> tools`, and uncheck "_Show Tooltips_" (You will not be able to use any plugins otherwise (also they like to get stuck to the screen which is very annoying)).


**2-** **ONLY IF YOU INSTALLED VKD3D PROTON**:  Go to: `Edit -> preferences -> Camera raw... -> performance` and set "_Use graphic processor_" to "_Off_"

## Launching Photoshop

Desktop entry should be created automatically. Open your application launcher and look for "Photoshop CC".

[image](https://github.com/GordonZed/photoshop-22-linux/blob/main/launcher-screenshot.png)

## Happy Shooping

Let me know if you have any issues, or if the install file links go down. I'll try to tweak and improve this when I can.
