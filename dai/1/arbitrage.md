---
layout: default
title: Dai
subtitle: arbitrage
description: Maker platform debt market
---

### Boom

Debt in exchange for collateral

- the system sells profits in exchange for peth (claim on collateral), which it burns.
- the value of peth relative to collateral increases
- the supply of dai increases
- collateral is backing more debt, reflected by the change in supply ratio to peth.

### Bust

Collateral in exchange for debt

- the system sells collateral from underwater positions (dai) in exchange for dai, which it burns
- where recovered collateral is insufficient it mints more, increasing the peth supply
- value of peth relative to collateral decreases
- the supply of dai decreases
- less debt being backed by collateral, reflected by the change in supply ratio to peth.

Both operations levy a spread - 3%, which is paid to?
Flat order book - no slippage.
Remember that ETH/USD & DAI/USD prices will also vary

- Arbitrage seekers race to buy at a discount when surplus or deficit exists.
- Sophisticated PETH holders can use bust to hedge against loss?

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
