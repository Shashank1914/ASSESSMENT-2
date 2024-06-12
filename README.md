# EcoCoin

EcoCoin is a basic ERC-20-like token implemented in Solidity, allowing for minting and burning of tokens on the Ethereum blockchain.

## Features

- **Token Details**: Public token name (`EcoCoin`) and symbol (`ECO`).
- **Minting**: Increase total supply and assign tokens to an address.
- **Burning**: Decrease total supply by destroying tokens from an address, with balance checks.

## Getting Started

### Prerequisites

- Node.js and npm (or yarn)
- Hardhat
- Ethereum wallet (e.g., MetaMask)

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

2. Run the script:
    ```bash
    npx hardhat run scripts/deploy.js --network <your-network>
    ```

### Interacting with the Contract

```javascript
const ecoCoin = await ethers.getContractAt("EcoCoin", <deployed_contract_address>);
await ecoCoin.mint(<address>, <amount>);
await ecoCoin.burn(<address>, <amount>);

