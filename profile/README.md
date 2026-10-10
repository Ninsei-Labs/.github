# Ninsei Labs

Ninsei is an RFQ atomic DEX for Monero: swaps between XMR and USDC, USDT or ETH at firm quotes from competing
market makers, with no custodian.

Every trade is a bilateral atomic swap between the user and a maker. On the EVM side the user's funds sit in an
escrow contract created for that one order, with no owner and no admin functions; on the Monero side, in a
one-time address that neither party can spend alone. Prices come from quotes signed by makers, and a recovery
file lets the user finish or unwind a trade without the Ninsei website.

## Repositories

- [sdk](https://github.com/Ninsei-Labs/sdk): the XMR and EVM swap engine for building a Ninsei interface,
  published on npm as [`@ninsei-labs/sdk`](https://www.npmjs.com/package/@ninsei-labs/sdk)

## Contributing

The rules for every repository are in [CONTRIBUTING.md](https://github.com/Ninsei-Labs/.github/blob/main/CONTRIBUTING.md).
