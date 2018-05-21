# User smart-contract and Opt-out subscription

While discussing payment options, opt-out subscription needs special mention. With the current state, it is not possible to opt-out subscription systems. In case of opt-in subscription user is prompted make payments when the subscription cycles is over. In case of non-payment services provided are stopped.

Although it gives option to user to unsubscribe whenever necessary it creates situation where user loses access to service due to opt-in mechanism. On the business side, most of the subscription businesses faces issue with high-churn rate and an opt-in mechanism might make the business unfeasible.

We create a possibility of opt-out subscription by creating user smart-contract. User smart-contract is essentially smart-contract on which user has sole modification access to. The smart-contract has details over all the opt-out subscription user has agreed to. Business smart-contract would have access to deduct the subscription amount after completion of subscription cycles. User can opt-out of a subscription by modifying/deleting that subscription from the smart-contract.

Another benefit which user smart-contract brings is it gives details of all subscriptions in one place.



## Example 





1. ~~Alice is browsing Bob's website.~~
2. ~~Alice likes a product and and decides to purchase it.~~ 
3. ~~Alice clicks on Payment button and is prompted for her ethereum address \(or ENS if she has one\)~~
4. ~~Alice fills in her address a function is called on her contract in ethereum blockchain which fires a request payment event for which the OPOCHWallet is listening to.~~
5. ~~Alice's OPOCH app generates a notification to approve the payment.~~
6. ~~Alice approves payment on OPOCH App and  payment is made on Bob's address/contract~~



  
  


