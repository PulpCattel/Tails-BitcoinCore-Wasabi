# Bitcoin Core installation

**DOWNLOAD**

Let’s use Tails to download Bitcoin Core. 

If Tails is correctly installed, you should be able to setup the [internet connection](https://tails.boum.org/doc/anonymous_internet/networkmanager/index.en.html) and open the Tor Browser. 

Linux installer can be found here https://bitcoincore.org/en/download/.

Verify the package downloaded and the official site.

As of now (Bitcoin block 595524), the Bitcoin Core PGP key fingerprint is: `01EA 5486 DE18 A882 D4C2  6845 90C8 019E 36C2 E964`

Extract your bitcoin.tar.gz file in the persistent storage.

`/Persistent`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; `/bitcoin-0.18.1` (Bitcoin Core launcher folder)   


**CREATE CONFIGURATION FILE**

In order to make it work with Tails and a USB, we need to slightly configure our bitcoin.conf file. 

*The configuration file is not automatically created; you can create it using your favorite plain-text editor. By default, Bitcoin (or bitcoind) will look for a file named 'bitcoin.conf' in the bitcoin data directory.*

(Source: https://en.bitcoin.it/wiki/Running_Bitcoin#Bitcoin.conf_Configuration_File)

Create a folder inside the persistent storage, e.g. `Bitcoin`, this’ll be the Bitcoin Core data directory. Create with text editor a bitcoin.conf file inside it.

`/Persistent`  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; `/bitcoin-0.18.1` (Bitcoin Core launcher folder)     
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; `/Bitcoin`  (Bitcoin Core data folder)   
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; `bitcoin.conf` (Configuration file)  

First we need pruning, since we likely don’t have >256GB in our storage. Add:

`prune=10000` for 10GB pruning.

(Source: https://bitcoin.org/en/full-node#reduce-storage)

Then we need to add a proxy to make Bitcoin Core work with Tor. Add:

`proxy=127.0.0.1:9050`

(Source: https://www.reddit.com/r/tails/comments/3ecttp/running_bitcoin_core_bitcoinqt_on_tails)

Your bitcoin.conf will look like this:

`prune=10000`  
`proxy=127.0.0.1:9050`

**LAUNCH BITCOIN CORE**

Assuming the 0.18.1 version, to launch Bitcoin Core browse to /bitcoin-0.18.1/bin, drag the “bitcoin-qt” file into a terminal and press enter. 

Bitcoin Core will ask you to choose a directory for the data folder. Leaving the default one will lead to Core being removed at shut down, so choose the directory previously created inside the persistent storage.

The blockchain synch will start, the time needed will widely change based on your configuration. 
On a laptop with 8GB ram, Intel core i5 3.4GHz, USB 3.0 and optical fiber internet, took ~ 24 hours.

Once the synching is over, the node is ready to use.

At every new session Bitcoin Core will ask you for the data directory, choose your custom data folder and click ok. 

**CHECK NEW PAYMENTS WITH BITCOIN CORE**

A simple way to check receiving payments is to open the Bitcoin Core console from *Window > Console* and type:

`importaddress address ‘’ false`  
or  
`importpubkey pubkey ‘’ false`

* `importaddress`/`importpubkey`: is the command.
* `address`/`pubkey`: is the address/publickey you wanna check.
*  `‘’`: is the label, with ‘’ you leave it blank.
* `false`: is the “rescan” argument and we need to set it to false cause pruned node cannot do rescan.

Type `help "command"` if you need help. e.g, `help importpubkey`

**DELETE/CREATE WALLET**

If you want to dispose of your wallet, delete wallet.dat from your data directory. Bitcoin Core will automatically create a new wallet.dat if none is found.

---
Next:  
[Install Wasabi](Wasabi_installation.md)
