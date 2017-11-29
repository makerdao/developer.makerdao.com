---
layout: default
title: Dai
subtitle: use cases
---

## Arbitrage

System operated debt market `tap` buys and sells Dai for PETH using external
reference price and target price feeds.

Will create opportunity for arbitrage across other exchanges where dai, ether,
usd is trading.

Flat order book - no slippage.

Remember that ETH/USD & DAI/USD prices will also vary

Sophisticated PETH holders can use boom & bust to hedge.

The system charges a stability fee on borrowed dai which it realises by selling dai in exchange for peth.

The system collects revenue by selling profits from stability fees in `dai` in exchange for collateral `peth` which is then burned.

who is going to buy the DAI at boom? are peth holders not going to want someone else to buy? but only peth holders can buy!!

PETH holders sell dai at boom. Where do they get the dai? They borrow, or buy it.

- Collateral holders can ensure they maintain a fixed percentage of the PETH supply.
- They will want to buy into dai before other PETH holders if bad debt threatens supply increase.
- And buy back into PETH as the system realises profit.

- Buy & Burn peth for dai.
- PETH holders can buy surplus `dai` to their advantage because it increases the value of PETH.
- value transfer DAI -> PETH -> DAI

System profits are realised to PETH holders by decreasing supply.

## Borrowing

Own & operate a CDP. Autonomous Dai-denominated loans by locking up ether as collateral.

## Leverage

It would be easy to write a contract that accepts ETH and gives you back a recursively leveraged CDP

Making an ERC20 token containing a CDP, which would kind of be like a leveraged
ETH token (think leveraged ETFs on NASDAQ), is something that has been
discussed.

- Basic
- Atomic
- Oasis Direct

## Stability

Buy dai on the open market as a shelter from volatility. Move value into dai
during a periods of uncertainty. Regular users don't have to know about the
advanced mechanics of Dai to take advantage of its stable value.
