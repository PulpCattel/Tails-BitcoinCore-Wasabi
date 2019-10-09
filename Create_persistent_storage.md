# Create persistent storage

Tails is awesome as an “amnesic” system, but we actually need to retain some files between different sessions, our full node for example. What Tails allow us to do is create an encrypted [LUKS](https://en.wikipedia.org/wiki/Linux_Unified_Key_Setup) volume.

It's extremely easy to do, but first give a look at the [warnings](https://tails.boum.org/doc/first_steps/persistence/warnings/index.en.html
)!

Remember that Tails is not a magic wand.

**CREATE PERSISTENT STORAGE**

* *1. Choose Applications > Tails > Configure persistent volume.*
* *2. Specify a passphrase of your choice in both the Passphrase and Verify Passphrase text boxes.*
* *3. Click on Create button.*
* *4. Wait for the creation to finish.*
* *5. The assistant shows a list of the possible persistence features. Each feature corresponds to a set of files or settings to be saved in the encrypted persistent storage.*
* *6. Click save*

(Source: https://tails.boum.org/install/clone/index.en.html#create-persistence)

We only need the [*Personal Data*](https://tails.boum.org/doc/first_steps/persistence/configure/index.en.html#index1h2) option, though a possible useful one is the [*GnuPG*](https://tails.boum.org/doc/first_steps/persistence/configure/index.en.html#index7h2).

I highly encourage you to leave every other option unchecked unless you have a very strong reason to do otherwise. 
Messing up with the persistent storage could nullify most of the Tails benefits.

(Source: https://tails.boum.org/doc/first_steps/persistence/configure/index.en.html)

**UNLOCK PERSISTENT STORAGE**

Shut down Tails and start it again, a new field called “Encrypted persistent storage” will appear at “Tails Greeter”. Entering your passphrase will unlock the storage. 

:warning: If you lose your passphrase, you lose access to your persistent storage! 

*Is it possible to recover the passphrase of the persistent volume?*

*No. The encryption of the persistent volume is very strong and it is not possible to recover the passphrase of the persistent volume. If the passphrase is weak enough, an attacker, using a brute force attack, could try many possible passphrases and end up guessing your passphrase.*

(Source: https://tails.boum.org/support/faq/index.en.html#index19h2)

:warning: Remember to be extra careful if you’ve to unlock your persistent storage on a non-Tails machine. 
Ideally, only use the USB drive as a booting device and unlock it only through Tails.  

**DELETE PERSISTENT STORAGE**

Fast way:

* *1. Start Tails from the USB stick on which you want to delete the persistent volume. Do not enable the persistent volume in Tails Greeter.*
* *2. Choose Applications ▸ Tails ▸ Delete persistent volume.*
* *3. Click Delete.*

Secure way:

* *1. Format the USB stick and create a single encrypted partition on the whole USB stick. This step deletes both Tails and the persistent volume.*
* *2. Securely clean all the available disk space on this new encrypted partition.*
* *3. Reinstall Tails on the USB stick.*
* *4. Start Tails from the USB stick and create a new persistent volume.*

(Source: https://tails.boum.org/doc/first_steps/persistence/delete/index.en.html)

---
Next:  
[Install Bitcoin Core](Bitcoin_Core_installation.md)
