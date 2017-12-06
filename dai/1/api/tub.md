---
layout: dai/api
title: Dai
subtitle: API
---

### Collateralized Debt

Pooled collateral can be locked up and used to borrow dai via records
known as CDPs (Collateralized Debt Positions).

#### Tub - a CDP Record Engine

The `tub` is the CDP record system.  An individual CDP is called a `cup`
(i.e. a small container), and has:

- `lad`: an owner
- `ink`: locked SKR collateral
- `art`: debt

It is crucial to know whether a CDP is well collateralised or not:
`safe(cup)` returns a boolean indicating this.

`safe` aggregates price information from the `vox` and the `tub` and
compares the reference value of a CDPs debt and collateral.

None of the `tub` acts are possible if they would transition a CDP
to unsafe.
