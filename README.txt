BITSF452_A2_15
+++++++++++++++++++++++++++++++++++++
GROUP 15 
+++++++++++++++++++++++++++++++++++++


We, Group 15, have created a smart contract which will make sure 2 things happen is a trustless e-commerce environment between a seller and buyers.

1. The product is dispatched by the seller only when the payment by the customer is confirmed.
2. The seller receives the money for the sold product only when they deliver the product.

We have also added 2 extra features to this contract
1. The customer is refunded if they haven't received the product or received a defective one
2. The customer can tip the seller for their delivery and this will be directly sent to the seller's account.


The owner first deploys the contract with the price of the product they want to sell and the address of the seller(which could be the owner themselves)
as parameters to the constructor. The variables "product_sent" and "product_delivered" are flags that can be set(made true) by only authorised personel.
These are initialised to false when the contract is first deployed. 

This selected permissions and authorization constraints are implemented using the modifiers. These are like pre-requisites/constraints to call/run a function.
The modifiers "OnlyOwner","OnlySeller","notOwner" and "notSeller" will help us implement thses constraints.


** The payMoney() function along with modifiers 'notOwner' and 'notSeller' will allow the customer to buy a product by sending money to the contract.
** The deliverProduct() function can be called only by the seller, and this function checks if the amount send by customer is the sufficient amount to start delivery 
   of the product(this is start dispatching the product). If the amount is correct they will start dispatch by setting 'product_sent' to true.
** The isProductdelivered() function will alow only the customer to notify the owner and seller if they received the product. 
   This function sets the 'product_delivered' to true/false based on customer input.
** The isProductDefective() function will allow the customer to notify if the product they received was defective
** The refund() function will allow the customer to get back their money if the product hasn't been delivered to them or when a defective product is delivered 
** The transferFund() function will send the money to the seller from the contract after the delivery is over
** The getbalance() function will return the balance of the contract
** The sendtip() function will take tip input from the customer and allows the customer to directly send the tip to the seller



To run this code:
1. Choose a seller ID and the cost of the product you wish to sell and input it to the contract and deploy
2. Choose a customer address and call the 'payMoney' function by sending some value. This is like the customer placing an order for the product.
3. Then call 'getbalance', we would get the correct amount into the contract.
4. Choose the seller's address and call the 'deliverProduct' function, this would start the delivery of the product 
5. Once customer recieves the product they call the 'isProductdelivered' function with status input.
6. If the customer didn't get the product delivered or didn't receive the product in good condition the owner can call the 'refund' function to refund the customer
7. If delivery is done and in good condition then the seller will receive their money.
8. The customer can send a tip if they wish, directly to the seller.
