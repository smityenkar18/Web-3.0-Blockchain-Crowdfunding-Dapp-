This project is a decentralized crowdfunding application (DApp) built using Web 3.0 technologies, including Ethereum smart contracts, React.js for the frontend, and ethers.js for interacting with the Ethereum blockchain. The DApp allows users to create and manage crowdfunding campaigns, donate to campaigns, and view details about campaigns and donations.

Project Structure
1. Crowdfunding.js

Imports:
- ethers: Ethereum library for interacting with the blockchain.
- React, useEffect, useState: React utilities.
- web3modal: Library for connecting to web3 wallet providers.
- Internal Imports:
- CrowdFundingABI, CrowdFundingAddress: ABI and contract address for the crowdfunding smart contract.
  
Functions:
- fetchContract(signerOrProvider): Utility function to fetch the contract instance.
- CrowdFundingContext: React context for state management.
- CrowdFundingProvider({ children }): Main provider component.
- Core Functionality:
- createCampaign: Function to create a new crowdfunding campaign.
- getCampaigns: Function to retrieve all campaigns.
- getUserCampaigns: Function to retrieve campaigns created by the connected user.
- donate: Function to donate to a campaign.
- getDonations: Function to retrieve all donations for a campaign.
- checkIfWalletConnected: Function to check if a wallet is connected.
- connectWallet: Function to connect a wallet.

State Management:
- titleData, currentAccount: State variables to manage the contract title and the current user account.
- Effects:
- Automatically checks if a wallet is connected when the component mounts.

2. Crowdfunding.sol

Smart Contract:
- Written in Solidity for deployment on the Ethereum blockchain.
- Structs:
- Campaign: Data structure to store campaign details.
  
Mappings:
- campaigns: Mapping to store campaigns by their ID.
- State Variables:
- numberOfCampaigns: Counter for the total number of campaigns.
  
Functions:
- createCampaign: Creates a new campaign and stores it in the campaigns mapping.
- donateToCampaign: Allows users to donate to a specific campaign.
- getDonators: Retrieves the list of donators and their donations for a specific campaign.
- getCampaigns: Retrieves all campaigns.
  
3. Deploy.js

Deployment Script:
- Uses Hardhat to deploy the CrowdFunding smart contract.
Main Function:
- Deploys the contract and logs the deployed contract address.
Error Handling:
- Catches and logs any errors that occur during deployment.

Features

Campaign Creation:
- Users can create new campaigns by providing a title, description, target amount, and deadline.
Campaign Listing:
- Fetch and display all campaigns from the blockchain.
User Campaigns:
- Filter and display campaigns created by the connected user.
Donations:
- Users can donate to campaigns using their Ethereum wallet.
Donation Tracking:
- Retrieve and display the list of donators and their contributions for each campaign.
Wallet Integration:
- Connect with MetaMask or other Ethereum wallets to interact with the DApp.

Setup and Deployment

1. Smart Contract Deployment:

- Use Hardhat to compile and deploy the CrowdFunding smart contract to the Ethereum network.
- Run Deploy.js script to deploy the contract.

2. Frontend Setup:

- Install dependencies with npm install.
- Start the React app with npm start.
- Ensure you have MetaMask installed and connected to the correct Ethereum network.

Usage

Create a Campaign:
- Connect your wallet.
- Fill in the campaign details and submit.

View Campaigns:
- Browse the list of all available campaigns.

Donate to a Campaign:
- Choose a campaign and donate using your Ethereum wallet.

View Donations:
- Check the details of donators and their contributions for a specific campaign.

Dependencies
- React.js: Frontend framework.
- ethers.js: Ethereum JavaScript library.
- web3modal: Library for connecting to web3 wallet providers.
- Solidity: Programming language for writing smart contracts.
- Hardhat: Ethereum development environment for deploying and testing contracts.
