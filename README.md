# Introduction
Follow the instructions in this README to create a flash drive that contains your password manager's (e.g. 1Password) master password. As long as this flash drive is plugged into your machine, you can use the hotkey 'pause break' (you can use whatever you like, I just chose a key I never use) to paste the password into the window you have focused on (e.g. 1Password login screen).

# Motivation
Password managers like 1Password let you use a master password to unlock access to the rest of your passwords. This means the master password must not be easy to guess, which can mean it can get lengthy to type and remember. This setup allows you to use a USB flash drive, in the same manner, you use a key to unlock the doors of your house. You plug it in and can paste your master password with a hotkey. You pull out the flash drive and you will no longer be able to paste the master password (the password is stored on the flash drive, it never touches the hard drive of the device you're logged into).

- **IMPORTANT**: if your flash drive gets lost or stolen, change your master password immediately! It also wouldn't hurt to have 2-factor authentication set up on your 1Password account just in case.

# Windows
- Install [APO USB Autorun](https://www.softpedia.com/get/System/System-Miscellaneous/APO-USB-Autorun.shtml)
- Ensure APO USB Autorun is enabled in the Startup apps list
- Add all files from the root of this repo to the root of the flash drive (e.g. no folders)
- Add your password to the secret.txt file. Only the password goes in this file, do not include spaces or newline characters that are not part of the password.
- Plugin the flash drive and press the 'pause break' (you can set a different key by modifying and recompiling the file send_secret.ahk) key on your keyboard to paste the password from secret.txt to your focused window.

# Ubuntu
- Install prerequisite applications:
   - `sudo apt update;sudo apt install xclip xdotool -y`
- Add this shortcut to Keyboard Shortcuts
   - Name: `Paste 1Password secret`
   - Command (make sure you set the path to your usb drive): `sh -c "xclip -sel clip /media/path_to_usb_drive/secret.txt;xdotool sleep .100 key ctrl+v;xclip -sel clip < /dev/null"`
   - Shortcut: `Pause` (push the 'pause break' button to assign)
      - Note: If you used a different key than 'pause break' and it has modifiers (e.g. shift, alt, ctrl), then you will want to increase the sleep value of the shortcut command, so you have time to press and remove all your fingers before xdotool sends `ctrl+v`.
     
References:
- https://www.howtogeek.com/326049/how-to-auto-run-windows-programs-when-you-plug-in-a-usb-drive/
- https://www.autohotkey.com/docs/AutoHotkey.htm
