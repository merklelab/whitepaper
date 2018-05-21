# APIs

~~In the recent past, the API economy has grown a lot. Businesses are using different APIs to delegate the work they don’t have expertise on\[\[viii\]\] enabling faster, cheaper and smarter work. We create APIs to enable cryptocurrency payments for the businesses~~.

Since the overhead for developers to learn blockchain and crypto currencies is very huge at the moment and moreover businesses want their teams to focus on their product, we provide ready to use API's to business which they can use just like in the centralised banking/payment gateway solution to handle their business specific payment schemes. 

Business hit `generateSmartContract()` function with their business specific JSON data to create the smart-contract. Apart from business use cases, businesses can provide private keys who can have access to these smart-contracts and funds, replicating their hierarchy for account management.  


The more details around APIs

{% api-method method="post" host="" path="/v1/deploy/" %}
{% api-method-summary %}
Deploy
{% endapi-method-summary %}

{% api-method-description %}
Deploys a Business Smart 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-form-data-parameters %}
{% api-method-parameter name="amount" type="string" required=false %}
Amount 
{% endapi-method-parameter %}
{% endapi-method-form-data-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
JSON object with transaction hash, which can be used to get contract address
{% endapi-method-response-example-description %}

```
{
    transaction_hash:  <string>,
    bsm_id: <string>
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

| **Endpoint** | **Method** | **Parameters** | **Returns** | Actions |
| --- | --- | --- | --- | --- | --- |
| /v1/deploy | POST |   | JSON Object:{transaction\_hash:  &lt;string&gt;,bsm\_id: &lt;string&gt;}  | Deploys  a Business Smart Contract based for the business based on the specifications provided in the parameters when calling this API. |
| /v1/update/&lt;bsc\_id&gt; | PUT |   | JSON Object:{transaction\_hash:  &lt;string&gt;} | Update your Business Smart Contract with new values provided in the parameters**.** |
| /v1/delete/&lt;bsc\_id&gt; | POST | JSON Object with fields to update.Eg.{accept\_token: OPCHOTC,token\_amount: 20} | JSON Object:{transaction\_hash: &lt;string&gt;}  | Delete your currently deployed BSC. This will make call self destruct on the contract, transferring any existing balance to your wallet address as well as returning the gas freed. |
| /v1/details/&lt;bsc\_id&gt; | GET |   | JSON Object | Lists all current details regarding the BSC Eg. Current Balance, Deployed address, Total payments etc.These details would be polled from blockchain or from IPFS. |
| /v1/details/&lt;bscid&gt;/&lt;user\_address&gt;  | GET |   | JSON Object | Lists the user specific details regarding that BSC like last payment date, number of active subscriptions etc. |

