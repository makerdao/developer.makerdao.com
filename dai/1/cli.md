---
title: Dai CLI
layout: dai/default
redirect_from:
 - /dai/1/reference/
---

### Dai CLI

The [Dai CLI](https://github.com/makerdao/dai-cli) is a client for command-line
interaction with the [core system]({{ "dai/1/api/" | relative_url  }}) contracts on
the Ethereum blockchain. It's built on [Seth](https://github.com/dapphub/seth),
the unix inspired, blockchain automation & open source finance toolkit,
maintained by the [DappHub](https://dapphub.com) collective.

#### Installing

Dai is distributed via [the Nix package manager](https://nixos.org/nix),
enabling cryptographically precise dependency tracking. First, install Nix
itself:

    $ curl https://nixos.org/nix/install | sh

Then add DappHub's distribution channel and install `dai`:

    $ nix-channel --add https://nix.dapphub.com/pkgs/dapphub $ nix-channel
    --update $ nix-env -iA dapphub.dai

See [dapp.tools](https://dapp.tools) for more software available through our
channel.

#### Upgrading

To upgrade Dai to the latest release, update the channel and then
reinstall:

    $ nix-channel --update
    $ nix-env -iA dapphub.dai

#### Configuration

Dai accepts the following options, which can be set as variables or passed as flags:

    -F --from  ETH_FROM      sender address
    -G --gas   ETH_GAS       gas quantity
    -C --chain SETH_CHAIN    remote node target (ethlive or kovan)
       --cup   DAI_CUP       cup ID for cup operations

These variables can also be exported via bash script at `~/.sethrc` along with any
other [Seth configuration](https://github.com/dapphub/seth#configuration).

#### Connecting to the blockchain

By default, Dai assumes a local RPC node running on the default port.

It can also be run against a remote [Infura](https://infura.io) node from a
machine with no local copy of the blockchain using the `--chain` flag.

Ethlive dai system status:

    dai --chain ethlive status

or access the Dai deployment on the Kovan testnet:

    dai --chain kovan status

#### Read commands

Public accessible dai system and cup info.

```
dai  air             get the amount of backing collateral
dai  axe             get the liquidation penalty
dai  caged           get time of cage event (= 0 if system is not caged)
dai  chi             get the internal debt price
dai  cup             show the cup info
dai  fee             get the governance fee
dai  fit             get the gem per skr settlement price
dai  fix             get the gem per sai settlement price
dai  fog             get the amount of skr pending liquidation
dai  gem             get the collateral token
dai  gov             get the governance token
dai  cap             get the debt ceiling
dai  ice             get the good debt
dai  ink             get the amount of skr collateral locked in a cup
dai  joy             get the amount of surplus sai
dai  lad             get the owner of a cup
dai  mat             get the liquidation ratio
dai  off             get the cage flag
dai  out             get the post cage exit flag
dai  par             get the accrued holder fee (ref per sai)
dai  per             get the current entry price (gem per skr)
dai  pie             get the amount of raw collateral
dai  pep             get the gov price feed
dai  pip             get the gem price feed
dai  pit             get the liquidator vault
dai  rap             get the amount of governance debt in a cup
dai  ray             parse and display a 27-decimal fixed-point number
dai  rho             get the time of last drip
dai  rhi             get the internal debt price (governance included)
dai  s2s             get the skr per sai rate (for boom and bust)
dai  sai             get the sai token
dai  sin             get the sin token
dai  skr             get the skr token
dai  tab             get the amount of debt in a cup
dai  tag             get the reference price (ref per skr)
dai  tapAsk          get the amount of skr in sai for bust
dai  tapBid          get the amount of skr in sai for boom
dai  tapGap          get the spread on `boom` and `bust`
dai  tau             get the time of last prod
dai  tax             get the stability fee
dai  tubAsk          get the amount of skr in gem for join
dai  tubBid          get the amount of skr in gem for exit
dai  tubGap          get the spread on `join` and `exit`
dai  vox             get the target price engine
dai  wad             parse and display a 18-decimal fixed-point number
dai  way             get the holder fee (interest rate)
dai  woe             get the amount of bad debt
```

#### Actions

Requires that the account specified at `ETH_FROM` be authorised to perform the
given command.

```
dai bite            initiate liquidation of an undercollateral cup
dai boom            buy some amount of sai to process joy (surplus)
dai bust            sell some amount of sai to process woe (bad debt)
dai cage            lock the system and initiate settlement
dai cash            cash in sai balance for gems after cage
dai cupi            get the last cup id
dai cups            list cups created by you
dai draw            issue the specified amount of sai stablecoins
dai drip            recalculate the internal debt price
dai exit            sell SKR for gems
dai free            remove excess SKR collateral from a cup
dai give            transfer ownership of a cup
dai heal            cancel debt
dai help            print help about sai(1) or one of its subcommands
dai join            buy SKR for gems
dai lock            post additional SKR collateral to a cup
dai open            create a new cup (collateralized debt position)
dai prod            recalculate the accrued holder fee (par)
dai safe            determine if a cup is safe
dai setAxe          update the liquidation penalty
dai setFee          update the governance fee
dai setHat          update the debt ceiling
dai setMat          update the liquidation ratio
dai setTapGap       update the spread on `boom` and `bust`
dai setTax          update the stability fee
dai setTubGap       update the spread on `join` and `exit`
dai setWay          update the holder fee (interest rate)
dai shut            close a cup
dai vent            process a caged tub
dai wipe            repay some portion of your existing sai debt
```
