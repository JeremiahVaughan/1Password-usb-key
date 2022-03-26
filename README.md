# Introduction
Follow the instructions in this README to create a flash drive that contains your password manager's (e.g. 1Password) master password. As long as this flash drive is plugged into your machine, you can use the hotkey alt+shift+control+p to paste the password into the window you have focused (e.g. 1Password login screen).

# Motivation
Password managers like 1Password let you use a master password to unlock access to the rest of your passwords. This means the master password must not be easy to guess, which can mean it can get lengthy to type and remember. This setup allows you to use a usb flash drive in the same manner you use a key to unlock the doors of your house. You plug it in and are able to paste your master password with a hotkey. You pull out the flash drive and you will no longer be able to paste the master password (the password is stored on the flash drive, it never touches the hard drive of the device your logged into).

 - **IMPORTANT**: if your flash drive gets lost or stolen, change your master password immediately! It also wouldn't hurt to have 2 factor authentication set up on your 1Password account just in case.

# Windows
 - Install [APO USB Autorun](https://www.softpedia.com/get/System/System-Miscellaneous/APO-USB-Autorun.shtml)
 - Ensure APO USB Autorun is enabled in the Startup apps list
 - Add all files from the root of this repo into the root of the flash drive
 - Add your password to the secret.txt file. Only the password goes in this file, spaces or new line charactures that are not part of the password.
 - Plug in the flash drive and press alt+shift+control+p to paste the password in secret.txt to your focused window.

# Ubuntu (comming soon)

References:
 - https://www.howtogeek.com/326049/how-to-auto-run-windows-programs-when-you-plug-in-a-usb-drive/
 - https://www.autohotkey.com/docs/AutoHotkey.htm
