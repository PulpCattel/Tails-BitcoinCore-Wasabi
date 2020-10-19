# Tails installation

**INSTALL INTO USB**

Now that you have your Tails.img, you need to install it into the USB. 

Based on your OS, pick the proper *Install from…* at step 3 from https://tails.boum.org/install/download/index.en.html and follow the guide to install it into the USB. 

You have your Tails OS ready to go.

At this point could be useful to open the instructions on another device, write them down or memorize them so you can continue after restarting.

**BOOT TAILS FROM USB**

We have to make the computer start from the USB stick.

Following the Tails step by step [guide](https://tails.boum.org/install/linux/usb/#back), first try to set the USB as booting device from [boot menu](https://www.computerhope.com/jargon/b/boot_menu.htm). 

If your USB doesn’t show in the boot list you probably need to disable “fast boot” or switch from “legacy mode” to “UEFI mode”, or the other way around, in the BIOS settings.

If something go south, try give a look at https://tails.boum.org/support/known_issues/index.en.html for already known issues. 

**TAILS GREETER**

* *1. One to two minutes after the Boot Loader Menu, another screen called Tails Greeter appears.*
* *2. In Tails Greeter, select your language and keyboard layout in the Language & Region section. Click Start Tails.*
* *3. After 15–30 seconds, the Tails desktop appears.*

(Source: https://tails.boum.org/install/linux/usb/index.en.html)

**TAILS**

This is your Tails desktop. If you've never used [Debian](https://en.wikipedia.org/wiki/Debian) before, you could feel a bit weird. Don't worry, the interface is clear and simple:

* top left: Application menu, here you find all inbuilt programs.
* top right: Wi-fi, account, settings and shutdown.
* bottom left: Activities overview, here you see your windows and applications, you can also start typing to search your applications, e.g., Wasabi.

(Source: https://tails.boum.org/doc/first_steps/introduction_to_gnome_and_the_tails_desktop/index.en.html)

Everything you do in every Tails session is lost by default upon shutdown, no trace or file will remain neither on your USB, neither on the computer. 

If you want to be extra careful, here it’s a list of interesting links:

https://tails.boum.org/doc/encryption_and_privacy/virtual_keyboard/index.en.html

https://redmine.tails.boum.org/code/issues/5356

https://tails.boum.org/support/known_issues/index.en.html#index3h1

---
Next:  
[Create persistent storage](Create_persistent_storage.md)
