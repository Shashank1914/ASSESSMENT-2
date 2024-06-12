# EcoCoin

EcoCoin is an ERC-20-like token implemented in Solidity. The contract includes functionalities to mint and burn tokens, providing a fundamental framework for managing tokens on the Ethereum blockchain.

## Table of Contents

- [Project Description](#project-description)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Compiling the Contract](#compiling-the-contract)
- [Usage](#usage)
  - [Deploying the Contract](#deploying-the-contract)
  - [Interacting with the Contract](#interacting-with-the-contract)
- [Contract Details](#contract-details)
  - [Functions](#functions)
- [Contributing](#contributing)
- [License](#license)

## Project Description

EcoCoin is designed as a simple and efficient token for various use cases. With basic minting and burning functionalities, EcoCoin can serve as the foundation for more complex token systems or as a standalone token for specific projects.

## Features

- **Token Details**: Publicly accessible token name and symbol.
- **Minting**: Increase the total supply and assign new tokens to a specified address.
- **Burning**: Decrease the total supply by destroying tokens from a specified address, ensuring the address has a sufficient balance.
- **Balance Tracking**: Mapping of addresses to token balances.

## Getting Started

### Prerequisites

To interact with the EcoCoin contract, ensure you have the following tools installed:

- [Node.js](https://nodejs.org/)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- [Hardhat](https://hardhat.org/)
- An Ethereum wallet like [MetaMask](https://metamask.io/)

### Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/ecocoin.git
    cd ecocoin
    ```

2. Install the dependencies:
    ```bash
    npm install
    # or
    yarn install
    ```

### Compiling the Contract

Compile the smart contract using Hardhat:
```bash
npx hardhat compile
