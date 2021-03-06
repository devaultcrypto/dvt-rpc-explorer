# DVT RPC Explorer

[![npm version][npm-ver-img]][npm-ver-url] [![NPM downloads][npm-dl-img]][npm-dl-url]

Forked from sickpig's [bch-rpc-explorer](https://github.com/sickpig/bch-rpc-explorer) (a fork of btc-rpc-explorer for Bitcoin Unlimited)

Simple, database-free DeVault blockchain explorer, via RPC. Built with Node.js, express, bootstrap-v4.

This tool is intended to be a simple, self-hosted explorer for the DeVault blockchain, driven by RPC calls to your own bitcoind node. This tool is easy to run but currently lacks features compared to database-backed explorers.

Whatever reasons one might have for running a full node (trustlessness, technical curiosity, supporting the network, etc) it's helpful to appreciate the "fullness" of your node. With this explorer, you can not only explore the blockchain (in the traditional sense of the term "explorer"), but also explore the functional capabilities of your own node.

Live demo available at: [https://exploredvt.com](https://exploredvt.com)

# Features

* Browse blocks
* View block details
* View transaction details, with navigation "backward" via spent transaction outputs
* View JSON content used to generate most pages
* Search by transaction ID, block hash/height, and address
* Optional transaction history for addresses by querying from ElectrumX and blockchair.com
* Mempool summary, with fee, size, and age breakdowns
* RPC command browser and terminal

## Prerequisites

1. Install and run a full, archiving node - [DeVault Releases](https://github.com/devaultcrypto/devault/releases). Ensure that your devault node has full transaction indexing enabled (`txindex=1`) and the RPC server enabled (`server=1`).
2. Synchronize your node with the DeVault network.
3. "Recent" version of Node.js (8+ recommended).
4. You could also run an [ElectrsCash](https://github.com/bitcoinunlimited/ElectrsCash) and configure the explorer to received data from it

## Instructions

```bash
npm install -g dvt-rpc-explorer
dvt-rpc-explorer
```

If you're running on mainnet with the default datadir and port, this Should Just Work.
Open [http://127.0.0.1:3002/](http://127.0.0.1:3002/) to view the explorer.

You may set configuration options in a `.env` file or using CLI args.
See [configuration](#configuration) for details.

### Configuration

Configuration options may be passed as environment variables
or by creating an env file at `~/.config/dvt-rpc-explorer.env`
or at `.env` in the working directory.
See [.env-sample](.env-sample) for a list of the options and details for formatting `.env`.

You may also pass options as CLI arguments, for example:

```bash
dvt-rpc-explorer --port 8080 --bitcoind-port 18443 --bitcoind-cookie ~/.devault/regtest/.cookie
```

See `dvt-rpc-explorer --help` for the full list of CLI options.

# Support

* [devault:qrt2ysz6hmkcndf6086q5v63lzgkmlf7egyxs8r3y8](devault:qrt2ysz6hmkcndf6086q5v63lzgkmlf7egyxs8r3y8)


[npm-ver-img]: https://img.shields.io/npm/v/dvt-rpc-explorer.svg?style=flat
[npm-ver-url]: https://www.npmjs.com/package/dvt-rpc-explorer
[npm-dl-img]: http://img.shields.io/npm/dm/dvt-rpc-explorer.svg?style=flat
[npm-dl-url]: https://npmcharts.com/compare/dvt-rpc-explorer?minimal=true

