# ETH-AVAX-Intermediate-Module3
MyToken: A Simple ERC20 Token Contract
This project implements a basic ERC20 token contract named "MyToken" with functionalities for minting, burning, and transferring tokens. You can deploy this contract using HardHat or Remix for educational purposes.

Important Note: This is a simplified example and lacks security features for production use. Do not use this code in a real-world environment without proper security audits and access control mechanisms.

Getting Started
Prerequisites:

Node.js and npm (or yarn) installed on your system.
A chosen deployment tool:
HardHat: https://hardhat.org/getting-started
Remix: https://remix.ethereum.org/
Deployment:

Choose your preferred deployment tool and follow the setup instructions:

a) HardHat:

i. Create a new HardHat project.
ii. Create a file named scripts/deploy.js with the following deployment script:

JavaScript
const { ethers } = require("hardhat");

async function main() {
  const MyToken = await ethers.getContractFactory("MyToken");

  // Replace with your desired token name, symbol, and initial supply
  const token = await MyToken.deploy("My Awesome Token", "MAT", 1000000);
  await token.deployed();

  console.log("Token deployed to:", token.address);
}

main()
  .then(() => process.exit(0))
  .catch((error) => {
    console.error(error);
    process.exit(1);
  });
Use code with caution.
content_copy
iii. Run the deployment script:

Bash
npx hardhat run scripts/deploy.js  # Replace with 'yarn hardhat run...' if using yarn
Use code with caution.
content_copy
This will deploy the contract and print the contract address.

b) Remix:

i. Open Remix and create a new file for contract interaction.
ii. Import the compiled contract artifact (artifacts/contracts/MyToken.sol/MyToken.json).
iii. Paste the deployed contract address obtained from HardHat deployment.
iv. Interact with the contract functions (mint, burn, and transfer inherited from ERC20) by specifying the recipient address and amount.

Functionality Overview
The MyToken.sol contract inherits from the standard ERC20 implementation provided by OpenZeppelin. Here's a breakdown of the key functionalities:

Constructor: Defines the token name (string memory name), symbol (string memory symbol), and initial supply (uint256 initialSupply) during deployment.
Mint Function (mint): Allows the contract owner (consider adding access control) to create new tokens and credit them to a specified address (address to, uint256 amount).
Burn Function (burn): Enables any token holder to burn their own tokens, reducing the total supply (uint256 amount).

## Author
Parteek
