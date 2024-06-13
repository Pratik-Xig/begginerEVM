# Token Creation Solidity Contract

The purpose of this project is to create a simple token using Solidity. The contract allows for minting and burning tokens, managing total supply, and checking balances of multiple addresses. 

## Description

This project involves developing a smart contract "MyToken" using the Solidity programming language. The contract defines a token with a name and abbreviation and keeps track of the total supply of tokens and all of these attributes are public in nature. It also maps addresses to the concurrent balances which are of uint data-type.ALso a constructor is used so that the values in the variables can be passed as the contract is deployed. The contract includes two functions: mint and burn. The mint function increases the token supply and the balance of the inputted address, while the burn function decreases the token supply and the balance of the inputted address, with a condition that the balance must be greater or equal to the value passed in as parameters in mint and burn functon.

## Getting Started


### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:


```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName;
    string public tokenAbbrev;
    uint public totalSupply;
    
    constructor(){
        tokenName="Pratik";
        tokenAbbrev="Prat";
        totalSupply= 0;
    }

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint value) public
    {
        totalSupply += value;
        balances[_address] += value;
    }

    // burn function
    function burn (address _address, uint value) public
    {
        if( balances[_address] >= value )
        {
        totalSupply -= value;
        balances[_address] -= value;
        }
    }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to 0.8.26, and then click on the Compile button.

Once the code is compiled, you can deploy the contract by clicking on the Deploy & Run Transactions tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can use it by calling the mint and burn functions. Click on the MyToken contract in the left-hand sidebar, and then click on the mint function. Enter the required parameters (address and value) and click on the transact button to execute the function. Similarly, to burn tokens, click on the burn function, enter the required parameters, and click on the transact button. Also you can click on the tokenName,tokenAbbrev,totalSupply buttons to check the result after the transactions completes.

## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Contributors names and contact info

Pratik Mishra 
pratikmishra.edu@gmail.com


## License

This project is licensed under the [NAME HERE] License - see the LICENSE.md file for details
