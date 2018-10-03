---
layout: default
title: Feeds
subtitle: price feed oracles
description: Exteral reference prices for the Maker platform
---

## Introduction

TODO

## Running a price feed

These are the steps required to deploy your own [price feed](https://github.com/makerdao/price-feed) and run a bot that updates its price regularly.

**NOTE: This guide has been tested with Ubuntu 16.04 or up.**

### Prerequisites

* Ethereum client like Parity or Geth running with an unlocked account.
* Node 6 or above.

### Installing DappHub's development tools

```
$ curl https://dapp.tools/install | sh
$ dapp pkg install seth
```

More info at [dapp.tools](https://dapp.tools)

### Installing setzer

[setzer](https://github.com/makerdao/setzer) is our tool to handle feeds.

```
$ dapp pkg install setzer
```
### Deploying your price feed

A [price feed](https://github.com/makerdao/price-feed) is the contract you'll be interacting with. We provide a FeedFactory that will create a price-feed for you.

FeedFactory is deployed at [0x435AD5CAE6eA3e065ce540464366b71Fba8f0c52](href="https://etherscan.io/address/0x435ad5cae6ea3e065ce540464366b71fba8f0c52). You will send a transaction to it and it will create your price-feed.

```
$ seth send 0x435AD5CAE6eA3e065ce540464366b71Fba8f0c52 --guess "create()(address)" -F [YOUR ACCOUNT] -G 700000 -P $(seth --to-wei 1 gwei)
```

This command sends a transaction to the FeedFactory's "create()" method, sending 700,000 gas, with a price of 1 gwei per gas. After it finishes, seth will print out the address of your price-feed.

### Setting up setzer

setzer expects a **/etc/setzer.conf** file that looks like this:

```
export ETH_FROM="YOUR ACCOUNT"
export SETZER_FEED="YOUR PRICE-FEED ADDRESS"
export SETZER_MEDIANIZER="0x729D19f657BD0614b4985Cf1D82531c67569197B"
export SETZER_SOURCES="LIST OF PRICE SOURCES"
```

The medianizer address is our current contract that reads several feeds and saves the median, which is then used as our official price source.

To select a list of price sources, run:

```
$ setzer price ls
```

You will see a list of sources along with their price. Select at least two and add their names (in lowercase) to **SETZER_SOURCES**, for example:

```
export SETZER_SOURCES="etherscan gdax gemini poloniex"
```
### Testing setzer bot

Once **setzer** is configured, it's time to test it. Run the following command:

```
$ setzer bot
```

It will initialize with your current configuration. The first time, your price-feed is empty so it will update with the new price.

Since you ran **setzer bot**, it will ask for confirmation before submitting a transaction. When prompted, select **Y** or **YES** to send the transaction. Wait for your transaction to be mined. If it's not mined in 90 seconds, setzer will try to resend with higher gas price. Accept the transaction until it passes.

After the price is set, **setzer bot** will continue to run, but only update if the price stored in the blockchain deviates from a certain percentage (+- 1% by default). At this point, you can stop setzer with **Ctrl + C** .

### Adding your feed to the medianizer

At this point you are updating your feed, but that's it. It's not yet part of of our official list of feeds. And the medianizer does not take it into account to calculate its price.

For that you need to contact us. Find us in [Maker Chat](https://chat.makerdao.com/channel/general) and propose running a feed. We value members of the community helping with this task, but please, contact us first!

### Running setzer bot automatically

Once you tried **setzer bot** and it's working, you can run it without user intervention. The command is:

```
$ setzer bot --auto
```

You can set your OS to run it automatically on boot, or have it run in the background. One suggestion is:

```
nohup setzer bot --auto > /path/to/bot.log 2>&1 &
```
And that's it!

Join us in the **#feeds** channel at [Maker Chat](https://chat.makerdao.com/channel/feeds) if you have any questions.
