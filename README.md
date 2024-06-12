# EcoCoin

EcoCoin is a simple ERC-20-like token implemented in Solidity. This contract allows for minting and burning of tokens, providing a basic framework for creating and managing a token on the Ethereum blockchain.

## Table of Contents

- [Project Description](#project-description)
- [Features](#features)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contract Details](#contract-details)
- [Contributing](#contributing)
- [License](#license)

## Project Description

EcoCoin is designed as an environmentally-friendly token, symbolized by `ECO`. This smart contract allows users to mint new tokens, increasing the total supply, and burn existing tokens, reducing the total supply. The contract provides a basic and secure way to manage a token on the Ethereum blockchain, making it a great starting point for developers looking to understand and build upon token functionalities.

## Features

- **Token Details**: Publicly accessible token name and symbol.
- **Minting**: Increase the total supply and assign new tokens to a specified address.
- **Burning**: Decrease the total supply by destroying tokens from a specified address, with balance checks to ensure security.
- **Balance Tracking**: Mapping of addresses to token balances.

## Getting Started

### Prerequisites

To interact with the EcoCoin contract, you will need:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Hardhat](https://hardhat.org/)
- An Ethereum wallet (e.g., [MetaMask](https://metamask.io/))

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/ecocoin.git
    cd ecocoin
    ```

2. Install dependencies:
    ```bash
    npm install
    # or
    yarn install
    ```

3. Compile the contract:
    ```bash
    npx hardhat compile
    ```

## Usage

### Deploying the Contract

To deploy the contract, you can use the Hardhat deployment script or interact with it directly through the Hardhat console.

1. Create a deployment script in `scripts/deploy.js`:
    ```javascript
    async function main() {
        const EcoCoin = await ethers.getContractFactory("EcoCoin");
        const ecoCoin = await EcoCoin.deploy();
        console.log("EcoCoin deployed to:", ecoCoin.address);
    }

    main().catch((error) => {
        console.error(error);
        process.exitCode = 1;
    });
    ```

2. Run the deployment script:
    ```bash
    npx hardhat run scripts/deploy.js --network <your-network>
    ```

### Interacting with the Contract

After deploying the contract, you can interact with it using the Hardhat console or through your dApp frontend.

```javascript
// Example: Minting tokens
const ecoCoin = await ethers.getContractAt("EcoCoin", <deployed_contract_address>);
await ecoCoin.mint(<address>, <amount>);
Contract Details
EcoCoin.sol
This Solidity contract includes the following functions:

mint(address addr, uint amount): Mints new tokens and assigns them to the specified address, increasing the total supply.
burn(address addr, uint amount): Burns tokens from the specified address, decreasing the total supply, with a check to ensure the address has sufficient balance.
Contributing
Contributions are welcome! Please follow these steps to contribute:

Fork the repository.
Create a new branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -m 'Add some feature').
Push to the branch (git push origin feature/YourFeature).
Open a pull request.
