# Ninsei Labs

Ninsei is an RFQ atomic DEX for Monero: swaps between XMR and USDC, USDT or ETH on Arbitrum at firm quotes from
competing market makers, with no custodian.

Every trade is a bilateral atomic swap between the user and a maker. On the EVM side the user's funds sit in an
escrow contract created for that one order, with no owner and no admin functions; on the Monero side, in a
one-time address that neither party can spend alone. Prices come from quotes signed by makers.

One recovery key of twelve words covers every swap a person makes. With it, the recovery page finds their swaps
on the settlement chain and moves their XMR out, without the Ninsei website and from any host.

## Repositories

- [sdk](https://github.com/Ninsei-Labs/sdk): the XMR and EVM swap engine for building a Ninsei interface,
  published on npm as [`@ninsei-labs/sdk`](https://www.npmjs.com/package/@ninsei-labs/sdk)
- [recovery-page](https://github.com/Ninsei-Labs/recovery-page): a static page that moves XMR out of a swap
  wallet with the recovery key, in the browser tab; anyone can serve it
- [denylist](https://github.com/Ninsei-Labs/denylist): the sanctioned EVM addresses (OFAC, UK, EU) that makers and
  interfaces refuse, checked weekly against the sources

## Contributing and security

The rules for every repository are in [CONTRIBUTING.md](https://github.com/Ninsei-Labs/.github/blob/main/CONTRIBUTING.md).
Report a vulnerability privately, as [SECURITY.md](https://github.com/Ninsei-Labs/.github/blob/main/SECURITY.md)
describes.
