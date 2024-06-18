# GauravSharma018-Solidiity_program-Beginner-
This program is a simple contract written in Solidity to give a basic idea about creating tokens and performing operations on them. The contract has multiple functions(i.e. burn and mint) that performs different tasks(i.e. increment and decrement). This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

# Description
Let’s Create a Token, Together! will now create your very own token! Well, not really, but kinda!
The contract has a public variables that store the details about the coin (Token Name, Token Abbrev, Total Supply)
The contract also has a mapping of addresses to balances (address => uint)
We have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount.
The contract also has a burn function, which works the opposite of the mint function, as it will destroy tokens. It takes an address and value just like the mint functions. It then deducts the value from the total supply and from the balance of the address.
Lastly, our burn function has conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

# Getting Started
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;
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
    string public tokenName = "ETHEREUM";
    string public tokenAbbrev = "ETH";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public{
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.7" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint function. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "mint" function and fill the address and value. Finally, click on the "transact" button to execute the function.

# Authors
Gaurav Sharma
Github -> GauravSharma018
gauravsharma1847@gmail.com

# License
This project is licensed under the MIT License - see the LICENSE.md file for details
