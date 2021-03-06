---
title: Proof of Stake minting guide
lang: en
ref: posguide
category: help
layout: page
permalink: /proof-of-stake-guide/
---

**Proof of Stake** (PoS) is a method to generate blocks Slimcoin inherited from Peercoin. In short: The more coins you have, the higher chance you get to find a block.

Block rewards are significantly lower in PoS than in PoW and PoB and they depend on the amount of Slimcoins you use to stake, although they are higher than in Peercoin. But on the other hand, PoS is basically risk-less income if your computer is secured and not compromised. And you contribute to the security of the system.

### Requirements

To mint coins via Proof of Stake, you need a relatively high amount of Slimcoins. 200-300 Slimcoins may be enough, but it's more secure if you try with about 1000 to 2000.

The coins must have not been moved for at least 30 days to qualify for Proof of Stake minting. If you move the coins, you will have to wait 30 days again.

**Important**: If you wallet is encrypted, you must unlock it to be able to mint (like in Proof of Burn minting). In the graphical client you find the *Unlock wallet* item in the *File* menu. In the graphical client, you should use the following command in the console (*Help* -> *Debug window* -> *Console* tab):

```walletpassphrase PASSPHRASE TIME true```

PASSPHRASE being your passphrase and TIME the time it should be unlocked (in seconds). The "1" means that the unlocking won't enable you to make transactions without entering the passphrase. If you want to unlock it indeterminately simply choose a large number, e.g. 999999999.

In the daemon, it is the same command, only you must add *slimcoind* before it.

### What must I do to mint?

**You have to do nothing!** Simply stay online with the client and the wallet unlocked, and you will eventually find a Proof of Stake block if you have enough mature coins in your wallet.

Your coins work for you automatically, like in some parts of the financial world :)

### The reserve balance (important!)

When you find a block, your staking coins will be frozen for some blocks to prevent certain kinds of attacks. During that time, you cannot do transactions with these staking coins.

To avoid this lock, you can set the so-called **reserve balance**. This is an amount of coins that won't be frozen if you find a block. But on the other hand it won't participate in "staking".

The reserve balance can be set in the graphical client in the

To permanently set a reserve balance, also if using the Slimcoin daemon (slimcoind), the **slimcoin.conf** configuration file and add:

```reservebalance=NUMBER_OF_COINS```

If reservebalance is set to 0, then you will stake with all coins.

### CPU and memory usage

Proof of Stake, in Slimcoin, requires a relative high amount of memory and CPU resources. The amount of resources depends on two factors:

* the number of coins you use to stake (the more coins, the more resources are needed)
* the number of inputs that are used to stake (the more inputs, the more resources)

**Note**: Inputs are an unit that is related to the number of transactions you received. In short: normally, for every transaction you received, your wallet will contain one input. The more transactions you receive, the more inputs your wallet will have to manage.

It is advisable that you *clean* your wallet if you have a large amount of inputs. For this purpose, simply make a single transaction to yourself.
