# Wasabi installation

(You can also refer to the [Wasabi setup on Tails](https://docs.wasabiwallet.io/using-wasabi/WasabiSetupTails.html#wasabi-setup-on-tails) included in the Wasabi documentation, which is based on this guide and more likely to be up to date)

**CREATE ADMIN PASSWORD**

You need sudo privileges to install Wasabi, at “Tails Greeter” create your admin password in “additional settings” and launch Tails.

(Source: https://tails.boum.org/doc/first_steps/welcome_screen/administration_password/index.en.html)

:bulb: If you don't want to activate root privileges, you can download Wasabi in .tar.gz format (other Linux) and extract it into the persistent storage.
This way, you can launch Wasabi from the terminal via `./wassabee` command without installing any .deb package.

(Source: https://docs.wasabiwallet.io/using-wasabi/InstallPackage.html#other-linux)

**DOWNLOAD**

Download for Debian/Ubuntu from:  
http://wasabiukrxmkdgve5kynjztuovbg43uxcbcxn6y2okcrsg7gb6jdmbad.onion (Tor onion link)  
or  
https://www.wasabiwallet.io/#download

Verify the PGP signature of the downloaded package. As of now (Bitcoin block 627049), the zkSNACKs' PGP key fingerprint is:   `6FB3 872B 5D42 292F 5992 0797 8563 4832 8949 861E`.

(Source: https://docs.wasabiwallet.io/using-wasabi/InstallPackage.html#debian-and-ubuntu)

You can now save your `Wasabi-X.X.X.deb` into the persistent storage, which at this point should look like this:

`/Persistent`  
&emsp; `/bitcoin-0.19.1` (Bitcoin Core launcher folder)  
&emsp; `/Bitcoin`  (Bitcoin Core data folder)  
&emsp; `/Wasabi-X.X.X.deb` (Wasabi installer)  

**WASABI DATA FOLDER**

As of version 1.1.11 Wasabi doesn’t offer easy ways, especially without command line, to change install directory. There is though a quick workaround.

Wasabi [saves session files](https://docs.wasabiwallet.io/FAQ/FAQ-UseWasabi.html#where-can-i-find-the-wasabi-data-folder) in `/Home/.walletwasabi/client`, you need to mark the “show hidden files” setting to see it.

Create a directory in your persistent with the same hierarchical structure, like this:

`/Persistent`  
&emsp; `/bitcoin-0.19.1` (Bitcoin Core launcher folder)  
&emsp; `/Bitcoin`  (Bitcoin Core data folder)  
&emsp; `/Wasabi-X.X.X.deb` (Wasabi installer)  
&emsp; `/.walletwasabi`  
&emsp; &emsp; `/client` (here we save our wallet files, filters and blocks)

After every session, when you’re done, navigate into `/Home/.walletwasabi/client` and copy the desired folders into your persistent directory.

Generally, you’d like to save the `Wallets` and `Blocks` folders.

The former contains your wallet information (e.g. keys, labels), while the latter includes the blocks needed to establish your balance.

Could be also nice to save the `BitcoinStore` folder, which contains the filters, so that you don’t have to download them again.

**INSTALL WASABI**

Copy and paste the `Wasabi-X.X.X.deb` file from `/Home/Persistent` into desktop.

Open the terminal and run:

`$cd Desktop`  
`$sudo dpkg -i Wasabi-X.X.X.deb`

Type the password you created at “Tails Greeter”.

([Info](https://help.ubuntu.com/lts/serverguide/dpkg.html) about dpkg)

Wasabi will show as a normal application in your activities overview menu, ready to start.

* Press [Windows key](https://en.wikipedia.org/wiki/Windows_key)
* Type "wasabi"
* Launch it

**LOAD FROM YOUR DATA DIRECTORY**

After the first time you save a Wasabi session, your persistent storage will look like:

`/Persistent`  
&emsp; `/bitcoin-0.19.1` (Bitcoin Core launcher folder)  
&emsp; `/Bitcoin`  (Bitcoin Core data folder)  
&emsp; `/Wasabi-X.X.X.deb` (Wasabi installer)  
&emsp; `/.walletwasabi`  
&emsp; &emsp; `/client` (here we save our wallet files, filters and blocks)  
&emsp; &emsp; &emsp; `/Wallets` (wallet files)  
&emsp; &emsp; &emsp; `/Blocks` (blocks)     
&emsp; &emsp; &emsp; `/BitcoinStore` (filters)  

To load your saved session, copy and paste the `.walletwasabi` folder into `/Home` before starting Wasabi.
 
You can save multiple copies of `.walletwasabi` in your persistent, each with different data:

`/Persistent`  
&emsp; `/bitcoin-0.19.1` (Bitcoin Core launcher folder)   
&emsp; `/Bitcoin` (Bitcoin Core data folder)  
&emsp; `/Wasabi` (General Wasabi folder)  
&emsp; &emsp; `/Wasabi-X.X.X.deb` (Wasabi installer)  
&emsp; &emsp; `/BitcoinStore` (No need to keep multiple copies of same filters)  
&emsp; &emsp; `/CoinJoin wallet`   
&emsp; &emsp; &emsp; `/.walletwasabi`   
&emsp; &emsp; &emsp; &emsp; `/client` (here we save our wallet files, filters and blocks)  
&emsp; &emsp; &emsp; &emsp; &emsp; `/Wallets` (wallet files)  
&emsp; &emsp; &emsp; &emsp; &emsp; `/Blocks` (blocks)  
&emsp; &emsp; `/watch-only coldstorage A`  
&emsp; &emsp; &emsp; `/.walletwasabi`  
&emsp; &emsp; &emsp; &emsp; `/client` (here we save our wallet files, filters and blocks)  
&emsp; &emsp; &emsp; &emsp; &emsp; `/Wallets` (wallet files)   
&emsp; &emsp; &emsp; &emsp; &emsp; `/Blocks` (blocks)  
&emsp; &emsp; `/watch-only coldstorage B`   
&emsp; &emsp; &emsp; `/.walletwasabi`    
&emsp; &emsp; &emsp; &emsp; `/client` (here we save our wallet files, filters and blocks)   
&emsp; &emsp; &emsp; &emsp; &emsp; `/Wallets` (wallet files)   
&emsp; &emsp; &emsp; &emsp; &emsp; `/Blocks` (blocks)

This is only a minor example, tune it to your own needs.

:warning: Remember to do backups!

---
Next:  
[Extra cool stuff](Extra_cool_stuff.md)
