# Blockchain Application Development

This is a repository for a three-hour training session held on the 19th March 2018, at the Digital Catapult Centre, Brighton, called [Intro to: Blockchain Application Development for Beginners](https://www.eventbrite.co.uk/e/intro-to-blockchain-application-development-for-beginners-tickets-42564510597). You can read more about the session's intentions in the original [introduction](/docs/intro.md). You can also find the [ session presentation](/presentation/dApp.md).

The session focused on the development of a dApp called [Provenator](https://github.com/glowkeeper/Provenator), which was the result of an academic paper that was published in a Special Issue of a Mary-Ann Liebert journal, Big Data: [Fake News - a Technological Approach to Proving Provenance Using Blockchains](https://doi.org/10.1089/big.2017.0071).

[Provenator](https://github.com/glowkeeper/Provenator) comprises two parts: a [React](https://reactjs.org/) frontend, and an [Ethereum](https://www.ethereum.org/) smart contract blockchain backend. During the session, we investigated both of those parts, and, in particular, focused on how they're glued together, including instantiating the Ethereum API from within React, interfacing with the smart contracts, and then sending and receiving asynchronous transactions to those contracts. Afterwards, we deployed the constituent parts to their respective distributed infrastructures - for the React front end, that was the InterPlanetary File System ([IPFS](https://ipfs.io/)), and for the smart contract backend, it was the test Ethereum network, [Rinkeby](https://www.rinkeby.io). Finally, we loaded the dApp into a browser and saw it in action.

## Credits

Original author: Steve Huckle, s dot huckle at sussex dot ac dot uk.

## Licensing

GNU General Public License v3.0

See [COPYING](/docs/COPYING.txt) to see the full text.
