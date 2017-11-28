---
layout: dai/api
title: Dai
subtitle: API
---

## Target Price Feed

The `vox` provides the Dai *target price*, given in terms of the reference
unit, by `par`. For example, `par == 2` with USD as the reference unit implies
a target price of 2 USD per Sai.

The target price can vary in time, at a rate given by `way`, which is the
multiplicative rate of change per second.

In Dai 1.0 the sensitivity, `how`, is set to zero. Adjustments to the target
price are made by adjusting the rate of change, `way`, directly with `coax`.
In future iterations, `how` may be non-zero and `way` adjustments will then
follow automatically via the feedback mechanism. The `vox` component is
subject to ongoing economic modelling research.
