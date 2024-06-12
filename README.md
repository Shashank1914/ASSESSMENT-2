EcoCoin
EcoCoin is an ERC-20-like token implemented in Solidity. The contract includes functionalities to mint and burn tokens, providing a fundamental framework for managing tokens on the Ethereum blockchain.

Table of Contents
Project Description
Features
Getting Started
Compiling the Contract
Usage
Interacting with the Contract
Contract Details
Functions
Contributing
Project Description
EcoCoin is designed as a simple and efficient token for various use cases. With basic minting and burning functionalities, EcoCoin can serve as the foundation for more complex token systems or as a standalone token for specific projects.

Features
Token Details: Publicly accessible token name and symbol.
Minting: Increase the total supply and assign new tokens to a specified address.
Burning: Decrease the total supply by destroying tokens from a specified address, ensuring the address has a sufficient balance.
Balance Tracking: Mapping of addresses to token balances.
Getting Started
Compiling the Contract
You can compile the contract directly on Remix:

Open Remix.
Create a new file named EcoCoin.sol and paste the contract code below.
Click on the "Solidity Compiler" tab and compile the contract.
Usage
Interacting with the Contract
After deploying the contract, you can interact with it using the deployed contract instance in Remix.

Minting Tokens:

Select the mint function.
Enter the address and amount to mint, then click "transact" and confirm the transaction.
Burning Tokens:

Select the burn function.
Enter the address and amount to burn, then click "transact" and confirm the transaction.
Contract Details
Public Variables
name: The name of the token, set to "EcoCoin". This is constant, so it cannot be reassigned.
symbol: The abbreviation of the token, set to "ECO". This variable is also constant.
totalSupply: The total supply of the token, initially set to 0.
Mapping
The contract uses a mapping balances to store the token balances of individual addresses.

Functions
mint(address addr, uint amount): Mints new tokens and assigns them to the specified address, increasing the total supply.
burn(address addr, uint amount): Burns tokens from the specified address, decreasing the total supply, with a check to ensure the address has sufficient balance.
Contributing
Contributions are welcome! Please follow these steps to contribute:

Fork the repository.
Create a new branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -m 'Add some feature').
Push to the branch (git push origin feature/YourFeature).
Open a pull request.
EcoCoin Solidity Code
solidity
Copy code
// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

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

contract EcoCoin {

    string public constant name = "EcoCoin";
    string public constant symbol = "ECO";
    uint public totalSupply = 0;

    // Mapping for token balances
    mapping(address => uint) public balances;

    // Mint function 
    function mint(address addr, uint amount) public {
        totalSupply += amount;
        balances[addr] += amount;
    }

    // Burn function 
    function burn(address addr, uint amount) public {
        require(balances[addr] >= amount, "Insufficient balance to burn");
        totalSupply -= amount;
        balances[addr] -= amount;
    }
}




