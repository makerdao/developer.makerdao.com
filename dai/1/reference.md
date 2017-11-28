---
layout: dai/default
title: Dai Reference
---

## CLI Reference

```
  Read commands:

   air             get the amount of backing collateral
   axe             get the liquidation penalty
   caged           get time of cage event (= 0 if system is not caged)
   chi             get the internal debt price
   cup             show the cup info
   fee             get the governance fee
   fit             get the gem per skr settlement price
   fix             get the gem per sai settlement price
   fog             get the amount of skr pending liquidation
   gem             get the collateral token
   gov             get the governance token
   hat             get the debt ceiling
   ice             get the good debt
   ink             get the amount of skr collateral locked in a cup
   joy             get the amount of surplus sai
   lad             get the owner of a cup
   mat             get the liquidation ratio
   off             get the cage flag
   out             get the post cage exit flag
   par             get the accrued holder fee (ref per sai)
   per             get the current entry price (gem per skr)
   pie             get the amount of raw collateral
   pep             get the gov price feed
   pip             get the gem price feed
   pit             get the liquidator vault
   rap             get the amount of governance debt in a cup
   ray             parse and display a 27-decimal fixed-point number
   rho             get the time of last drip
   rhi             get the internal debt price (governance included)
   s2s             get the skr per sai rate (for boom and bust)
   sai             get the sai token
   sin             get the sin token
   skr             get the skr token
   tab             get the amount of debt in a cup
   tag             get the reference price (ref per skr)
   tapAsk          get the amount of skr in sai for bust
   tapBid          get the amount of skr in sai for boom
   tapGap          get the spread on `boom` and `bust`
   tau             get the time of last prod
   tax             get the stability fee
   tubAsk          get the amount of skr in gem for join
   tubBid          get the amount of skr in gem for exit
   tubGap          get the spread on `join` and `exit`
   vox             get the target price engine
   wad             parse and display a 18-decimal fixed-point number
   way             get the holder fee (interest rate)
   woe             get the amount of bad debt

  Commands:

   bite            initiate liquidation of an undercollateral cup
   boom            buy some amount of sai to process joy (surplus)
   bust            sell some amount of sai to process woe (bad debt)
   cage            lock the system and initiate settlement
   cash            cash in sai balance for gems after cage
   cupi            get the last cup id
   cups            list cups created by you
   draw            issue the specified amount of sai stablecoins
   drip            recalculate the internal debt price
   exit            sell SKR for gems
   free            remove excess SKR collateral from a cup
   give            transfer ownership of a cup
   heal            cancel debt
   help            print help about sai(1) or one of its subcommands
   join            buy SKR for gems
   lock            post additional SKR collateral to a cup
   open            create a new cup (collateralized debt position)
   prod            recalculate the accrued holder fee (par)
   safe            determine if a cup is safe
   setAxe          update the liquidation penalty
   setFee          update the governance fee
   setHat          update the debt ceiling
   setMat          update the liquidation ratio
   setTapGap       update the spread on `boom` and `bust`
   setTax          update the stability fee
   setTubGap       update the spread on `join` and `exit`
   setWay          update the holder fee (interest rate)
   shut            close a cup
   vent            process a caged tub
   wipe            repay some portion of your existing sai debt
```
