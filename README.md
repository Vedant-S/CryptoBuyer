___________________________________________________________________________________________________________________________________
# CryptoBuyer - Decentralized Marketplace on Etherem Blockchain:
___________________________________________________________________________________________________________________________
CryptoBuyer is a prototype. It is a Marketplace that runs over the Etherem Blockchain. It is able to manage products (and orders, too).

Since it runs over the blockchain it doesn't need to have any server.
___________________________________________________________________________________________________________________________________
### How to use it:
___________________________________________________________________________________________________________________________________
You can run it by yourself.
In order to run this files you have to use something that inject Web3 into the webpage, the simplest way is to use Chrome with [MetaMask Extension](https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn) installed.

Remember, if you would like to use your machine to use it, you have to run a webserver (and not `file://`), otherwise MetaMask cannot inject the code due security restrictions.
___________________________________________________________________________________________________________________________________
## Contract:
___________________________________________________________________________________________________________________________________
The contract is developed using Solidity. It is actually deployed over Rinbeky Ethereum Test Net. You can you this code to understand how Solidity works. In order to deploy your own contract, you can refers to [this page]().
___________________________________________________________________________________________________________________________________
#### API
___________________________________________________________________________________________________________________________________
###### getOwnOrders() returns(uint[])
Returns the ids of the orders that refers to product sold by the `msg.sender`.
___________________________________________________________________________________________________________________________________
###### getProductIdsBySeller(address \_seller) returns(uint[])
Returns the ids of product sold by specific address.
___________________________________________________________________________________________________________________________________
###### buyProduct(uint \_id, uint32 \_quantity, string \_shippingAddress) payable
Is the only payable function of the contract. If the `msg.value` is equal to the price of the product with id equals to `_id`, then decrease the product avaiable quantity and create an order.
___________________________________________________________________________________________________________________________________
###### orders
This is the dynamic arrays that stores all the orders created. The Order has the following structure:

```solidity
struct Order {
        string shippingAddress;
        uint32 quantity;
        uint productId;
    }
```
___________________________________________________________________________________________________________________________________
###### addProduct(string \_n, string \_d, uint \_p, uint \_q)
This function add a product to `products` dynamic array. Set the linked proprieties stored into the following self-described maps:

```solidity
	mapping(uint => address) public productToSeller;
    mapping(address => uint32) public sellerProductCounter;
```

At the end generated the following event `NewProductCreated(address seller, uint productId);`.
___________________________________________________________________________________________________________________________________
###### removeProduct(uint \_productId)
This function delete the product from the `products` array. It can be executed only by the product's seller.
___________________________________________________________________________________________________________________________________
## What's next:
The orders are not yet implemented.
___________________________________________________________________________________________________________________________________
### Author:
----------------------------------
```diff
+ Vedant Shrivastava | vedantshrivastava466@gmail.com
````
