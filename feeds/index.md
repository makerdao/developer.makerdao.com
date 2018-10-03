---
layout: default
title: Feeds
subtitle: price feed oracles
description: Exteral reference prices for the Maker platform
---

## Overview

The reference price (ETHUSD) for the Maker system is provided via an oracle
(the `medianizer`), which collates price data from a number of external price
[feeds](https://makerdao.com/feeds/).

#### Price Feeds

Independent price feed operators constanly monitor the reference price across a
number of external sources and will submit updates to the blockchain when:

1. Source price differs to the most recently submitted price by more than
   the defined amount (currently 1%)
2. Last price update was more than 6 hours ago.

The following providers are used as feed sources:

- [bitbay](https://bitbay.net)
- [bitfinex](https://bitfinex.com)
- [bittrex](https://bittrex.com)
- [cex](https://cex.io)
- [coinbase](https://coinbase.com)
- [cryptocompare](https://cryptocompare.com)
- [etherscan](https://etherscan.io)
- [gdax](https://gdax.com)
- [gemini](https://gemini.com)
- [hitbtc](https://hitbtc.com)
- [kraken](https://kraken.com)
- [livecoin](https://livecoin.net)
- [poloniex](https://poloniex.com)
- [yobit](https://yobit.net)

Price feed operators may configure their instances to obtain price data from any
of these sources.

Price updates are written to the blockchain via [price feed] contracts which
are deployed and owned by feed operators. Price feed contracts which have been
whitelisted by the `medianizer` are able to forward their prices for inclusion in
the medianized price.

[price feed]: https://github.com/makerdao/price-feed

#### The Medianizer

The [medianizer] is the smart contract which provides Makers trusted reference price.

[medianizer]: https://etherscan.io/address/0x729D19f657BD0614b4985Cf1D82531c67569197B

It maintains a whitelist of price feed contracts which are allowed to post
price updates and a record of recent prices supplied by each address. Every
time a new price update is received the median of all feed prices is
re-computed and the medianized value is updated.

Permissions:

The adding and removal of whitelisted price feed addresses is controlled via
governance, as is the setting of the `min` parameter - the minumum number of
valid feeds required in order for the medianized value to be considered valid.
