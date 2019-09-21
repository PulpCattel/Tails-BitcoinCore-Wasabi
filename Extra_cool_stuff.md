# Extra cool stuff

**AIR-GAP WITH HARDWARE WALLET**

This setup works wonderfully for a coldstorage. 

Keep only your watch-only wallet in the persistent and use Wasabi (easier) or Bitcoin Core (harder) to build and broadcast PSBT (partially signed Bitcoin transaction).

https://github.com/bitcoin/bitcoin/blob/master/doc/psbt.md

https://github.com/Coldcard/firmware/blob/master/docs/bitcoin-core-usage.md

https://coldcardwallet.com/docs/quick

https://www.youtube.com/watch?v=aU8ysH9JH9M

**LEVERAGE THE BEAUTY OF TAILS**

The “fire and forget” nature of Tails is incredibily powerful for Bitcoin operation. 

You can, for example, keep a tool like [Ian Coleman’s html](https://github.com/iancoleman/bip39) on your persistent storage. 

Drop it into the desktop of Tails and generate addresses, check your seed + passphrases, export single private keys, exc… 

Shutdown the computer at the end and no trace will remain. If you want to be extra careful, do it in a offline session and without unlocking the persistent storage. 

You can also manage privacy-hungry wallets. 

Maybe you have 24 words on paper and a passphrase in your mind, and this wallet is extremely sensible and need to leave no trace. 

Use it in a Tails session and shutdown at the end. 

**TAKE ADVANTAGE OF YOUR FULL NODE**

Bitcoin Core offers many features and most of them work also in pruned mode. 

**LINUX ADVANCED USERS**

Should be possible, using command line, to set custom Wasabi directory.

https://github.com/zkSNACKs/WalletWasabi/issues/763

https://github.com/zkSNACKs/WalletWasabi/pull/1368

https://old.reddit.com/r/WasabiWallet/comments/9s7d1v/run_wasabi_in_portable_mode_from_usb/?st=k0r1vj19&sh=cc08530c

**OFFLINE SETUP**

Using Tails + persistent storage completely offline can be useful to create your personal "hardware wallet", you can use it as part of a multisig for example.

---

**That's all folks.**

**Stay safe out there.**

---
Next:  
[Bibliography](Bibliography.md)
