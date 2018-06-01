# Decentralized Fiat-Crypto P2P Marketplace

Opoch makes acquiring cryptocurrencies a truly peer-to-peer transaction without any 3rd party holding users' assets. For a great user experience, Opoch aims to achieve this exchange in under a minute, utilizing current and upcoming technologies.

The transaction cycle can be divided into 3 parts:  
1. Search and Discovery  
2. Crypto asset transfer  
3. Fiat-transfer

To reduce the overall latency and cost of completion of a transaction we combine off-chain and on-chain mechanism.

The **search and discovery** aspect of trade is completed off-chain. The user creates orders with their desired price and relevant order details. The counter-party can then search between multiple orders and select the most relevant among them. Being mobile first allows Opoch to utilise notification systems, user live status, location services, etc. in order to innovate freely and enable near-instant matching of counter-parties.

Once the order is matched, **crypto-asset transfer** is completed on chain. We enable these transfers with smart contract escrows for smart contract enabled blockchain assets, and with multi-sig transactions for Bitcoin and similar blockchains.

The **fiat currency transaction** is done peer-to-peer while the crypto-assets are held in escrows. The peer-to-peer transactions allows users to trade cryptocurrencies with fiat currency via any payment channel prevalent in that geography. For eg. _M-pesa in Kenya, Alipay in China, PayTm in India_ and Cash in all geographies.

There are four participants in this exchange and roles of these are briefly described below:

1. **Buyer:** Creates new order or interacts with an existing order.
2. **Seller**: Creates new order or interacts with an existing order.
3. **Relayer:** Helps in order discovery by providing a platform, and paying for transaction fees if a user is unable to provide for fees him/herself.
4. **Arbiter:** Arbiter helps solve the dispute if and when it arises. 

![](.gitbook/assets/screen-shot-2018-05-13-at-11.32.36.png)

* Buyer creates an off-chain bid on relayer to buy OPCH Tokens.
* Relayer broadcasts the bid on it's platform and updates it's order book.
* Seller finds Buyer's bid on Relayer's platform and requests to full-fill the bid.
* Relayer connects Buyer and Seller so that they can finalise the terms.
* Seller signs a **message** with his private key and relays it to the Relayer to be sent to blockchain, after finalizing terms with Buyer.
* Relayer verifies the message and sends transaction to blockchain and escrow is created.
* Buyer is notified and proceeds to transfer fiat to Seller by the payment method mutually agreed.
* Seller receives payment and releases the escrow, Arbiter and Relayer get their fees and Buyer receives the token.

The message signed by seller has following data. This is required to create escrow between buyer and seller and giving fees to relayer and arbiter.

| **Name** | **Type** | **Description** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sellerAddress | address | Address of Seller |
| buyerAddress | address | Address of Buyer |
| arbiterAddress | address | Address of Arbiter |
| arbiterFees | uint256  | Fees to Arbiter |
| relayerAddress | address | Address of Relayer |
| relayerFees | uint256 | Fees to Relayer |
| tokenAmount | uint256 | Amount of token in escrow |
| fiatAmount | uint256 | Amount of fiat to be paid |
| expiration | uint256 | Expiration time of escrow |
| v, r, s | uint8, bytes32, bytes32 | ECDSA Signature of above parameters. |





