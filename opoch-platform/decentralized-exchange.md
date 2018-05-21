# Decentralized Crypto Exchange

Decentralized exchange is a necessary bridge between users and the broader ecosystem. With the rise in number of cryptocurrencies, it would be impractical to expect that users would hold several cryptocurrencies in their wallet. Yet, they would like to access the ecosystem and the niche possibilities opened by each of these cryptocurrencies. Decentralized exchange built using KyberNetwork allows users to acquire cryptocurrencies as and when needed.

 

![Figure showing exchange of digital asset on Opoch using Kyber](../.gitbook/assets/screen-shot-2018-05-11-at-19.19.19.png)

**Kyber Network**

Kyber Network is trustless decentralized exchange service which allows instant exchange and conversion of digital assets \[Citation\]. 

Kyber Network builds a decentralized exchange which does not have a order-book. Instead of that it uses concept of liquidity pools which help get the exchange price between two tokens upfront. User is able to complete the token exchange instantaneously at this price. 

Kyber Network provide APIs to integrate these services with other applications.

**Kyber Network APIs**

To complete a exchange the following function needs to be called:

> ```text
>     function trade(
>         ERC20 source,
>         uint srcAmount,
>         ERC20 dest,
>         address destAddress,
>         uint maxDestAmount,
>         uint minConversionRate,
>         address walletId
>     )
> ```

This function converts the `source` token to `dest` token and sends it to `destAddress`.

Details around various parameters are as follows:

| **Parameter** | **Type** | **Details** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| source | address | The address of source token. |
| srcAmount | uint | Amount of source token to be converted. |
| dest | address | The address of token to be recieved. |
| destAddress | address | The address where the destination token needs to be sent. In our case it would same address of user. |
| maxDestAmount | uint | Maximum destination token amount. |
| minConversionRate | uint | Minimal conversion rate at which exchange should occur. |
| walletId | address | The id of service provider. In this case Opoch Id. |

### Cross-Chain Interaction

Though Kyber Network integration allows users to exchange cryptocurrency built over ethereum blockchain \(the majority\) instantaneously. It is not possible to exchange assets of other blockchains with this.   
  
We create cryptocurrency pool managed via smart contract. This would allow users to do cross chain transfers. 

![Figure showing cross-blockchain exchange of digital assets](../.gitbook/assets/screen-shot-2018-05-12-at-22.45.31.png)

The user transfers fund from the source blockchain to the smart contract cryptocurrency pool, while specifying the desired blockchain asset and address for receiving it. When the transfer on the first blockchain is complete, the other side of smart contract managed pool would release the required crypto assets to the mentioned address.





