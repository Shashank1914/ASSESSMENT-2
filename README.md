
EcoCoin
EcoCoin is an ERC-20-like token implemented in Solidity. The contract includes functionalities to mint and burn tokens, providing a fundamental framework for managing tokens on the Ethereum blockchain.

Table of Contents
Project Description
Features
Getting Started
Prerequisites
Installation
Compiling the Contract
Usage
Deploying the Contract
Interacting with the Contract
Contract Details
Functions
Contributing
License
Project Description
EcoCoin is designed as a simple and efficient token for various use cases. With basic minting and burning functionalities, EcoCoin can serve as the foundation for more complex token systems or as a standalone token for specific projects.

Features
Token Details: Publicly accessible token name and symbol.
Minting: Increase the total supply and assign new tokens to a specified address.
Burning: Decrease the total supply by destroying tokens from a specified address, ensuring the address has a sufficient balance.
Balance Tracking: Mapping of addresses to token balances.
Getting Started
Prerequisites
To interact with the EcoCoin contract, ensure you have the following tools installed:

Node.js
npm or yarn
Hardhat
An Ethereum wallet like MetaMask
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/ecocoin.git
cd ecocoin
Install the dependencies:

bash
Copy code
npm install
# or
yarn install
Compiling the Contract
Compile the smart contract using Hardhat:

bash
Copy code
npx hardhat compile
Usage
Deploying the Contract
Create a deployment script in scripts/deploy.js:

javascript
Copy code
async function main() {
    const EcoCoin = await ethers.getContractFactory("EcoCoin");
    const ecoCoin = await EcoCoin.deploy();
    console.log("EcoCoin deployed to:", ecoCoin.address);
}

main().catch((error) => {
    console.error(error);
    process.exitCode = 1;
});
Run the script:

bash
Copy code
npx hardhat run scripts/deploy.js --network <your-network>
Interacting with the Contract
After deploying the contract, you can interact with it using the Hardhat console or through your dApp frontend.

javascript
Copy code
const ecoCoin = await ethers.getContractAt("EcoCoin", <deployed_contract_address>);
await ecoCoin.mint(<address>, <amount>);
await ecoCoin.burn(<address>, <amount>);
Contract Details
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
Please ensure your code adheres to the existing style conventions and passes all tests.

License
This project is licensed under the MIT License - see the LICENSE file for details.

csharp
Copy code

### Explanation of the Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;
Explanation: Specifies the license (MIT) and the version of Solidity (0.8.25) used.
solidity
Copy code
contract EcoCoin {
    string public constant name = "EcoCoin";
    string public constant symbol = "ECO";
    uint public totalSupply = 0;
Explanation: Defines the contract EcoCoin. It declares public constant variables for the token name and symbol, and a public variable totalSupply initialized to 0.
solidity
Copy code
    mapping(address => uint) public balances;
Explanation: Declares a public mapping to store the balances of addresses.
solidity
Copy code
    function mint(address addr, uint amount) public {
        totalSupply += amount;
        balances[addr] += amount;
    }
Explanation: Defines the mint function, which increases totalSupply and the balance of addr by amount.
solidity
Copy code
    function burn(address addr, uint amount) public {
        require(balances[addr] >= amount, "Insufficient balance to burn");
        totalSupply -= amount;
        balances[addr] -= amount;
    }
}
Explanation: Defines the burn function, which decreases totalSupply and the balance of addr by amount, only if addr has sufficient balance.
