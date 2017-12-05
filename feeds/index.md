---
layout: default
title: Feeds
subtitle: price feed oracles
description: Exteral reference prices for the Maker platform
---

## Overview

The reference price (ETHUSD) for the Maker system is provided via an oracle,
the Medianizer, which collates data from a number of external price feeds.

### Price Feeds

Independent price feed operators constanly monitor the reference price across a
number of external sources and will submit updates via a price feed contract on
the blockchain when:

- the external price differs to the last submitted price by more than the
  prescribed amount (currently 1%)
- the last price update was more than 6 hours ago.

The following exchanges are used as sources:

- Poloniex
- Bitfinex
- Kraken

Price feed operators may configure their instances to use any of these sources.

### The Medianizer

TODO
