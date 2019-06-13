---
layout: oasis/api
title: Oasis Markets API
description: Public rest endpoints for markets data
apiVersion: 2
---

### REST API v2

Public REST endpoints for Oasis markets data.

#### Supported markets

Currently the following token pairs are supported (`base`/`quote`):
- WETH/DAI
- MKR/WETH
- MKR/DAI
- DGD/WETH
- REP/WETH
- RHOC/WETH

#### Notes

- No rate limiting
- No API key required
- All timestamps use ISO 8601 format (e.g. `2019-06-13T10:49:40.639Z`)
- All public endpoints use GET requests

#### Freshness

- Responses may be cached and shoult not be treated as live. Timestamps
  indicate the exact time at which the data should be considered valid.
