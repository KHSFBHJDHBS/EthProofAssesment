# Hello World

This Solidity program is a simple program that demonstrates the basic syntax and functionality of the "revert" ,"require" and "assert" statements in Solidity programming language. 

## Description

This program is a simple contract written in Solidity.The contract has three functions that show the working of "revert","require" and "assert" statements respectively. 
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.8.18 <0.9.0;

contract MyNewContract {
    uint public orderCount;
    
    struct Order {
        address client;
        uint pizzaSelection;
        bool delivered;
    }

    mapping(uint => Order) public orders;

    function placeOrderOld(uint pizzaSelection) public payable returns (uint){
        if(msg.value >= 1 ether) {
            Order memory newOrder = Order(msg.sender, pizzaSelection, false);
            orderCount++;
            orders [orderCount] = newOrder;
        }
        else{
            revert("the required payment amount is not met.");
        }
        return orderCount;
    }
    
    function placeOrder(uint pizzaSelection) public payable returns (uint){
        require(msg.value >= 1 ether,"the required payment amount is not met.");
        Order memory newOrder = Order(msg.sender, pizzaSelection, false);
        orderCount++;
        orders [orderCount] = newOrder;
        return orderCount;
    }

    function delivered(uint orderNumber) public {
        orders [orderNumber].delivered = true;
        assert(orders [orderNumber].delivered == true);
    }
    
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile Module1Proj.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "Module1Proj" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the PlaceOrder function. Click on the "Module1Proj" contract in the left-hand sidebar, and then click on the "PlaceOrder" function

## Authors

Praveen


## License

This project is licensed under the GNU General Public License version 3.
