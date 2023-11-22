# SolidityLearning-Examples
In this repository, you should be able to learn solidity coding for smart contracts from basic to advanced level use of concepts

**In Progress**

**Table of Contents**

**1.** SimpleStorage Contract

**2.** StorageFactory Contract

**3.** FundMe Contract

**So the first Three Exercises are done in Remix IDE, now as we gained some knowledge let's take it to the next step**

**4.** Web3_py_simple_storage using VS Code, Web3 and Ganache
**********************************************************************************************************************************************************************************

**1.**
## SimpleStorage Contract

The `SimpleStorage` contract is a basic example of a smart contract written in Solidity, designed to run on the Ethereum blockchain. It demonstrates fundamental concepts of Ethereum smart contracts, such as state variables, structs, arrays, mappings, and functions.

### Features

#### 1. State Variable
   - `favouriteNumber`: A `uint256` state variable to store a favorite number.
   
#### 2. Struct
   - `People`: A struct representing a person, containing a `uint256` for the favorite number and a `string` for the person's name.
   
#### 3. Dynamic Array
   - `people`: A public dynamic array of `People` structs, allowing the storage of multiple people's information.
   
#### 4. Mapping
   - `nameToFavouriteNumber`: A mapping from a person's name (string) to their favorite number (uint256). This provides a quick way to retrieve a person's favorite number using their name.
   
#### 5. Functions
   - `store(uint256 _favouriteNumber)`: A public function that allows storing a favorite number in the `favouriteNumber` state variable.
   - `retrieve()`: A public view function that returns the stored favorite number. Since it's a view function, it doesn't modify the contract's state and can be called without making a transaction.
   - `addPerson(string memory _name, uint256 _favouriteNumber)`: A public function to add a person's information to the `people` array and update the `nameToFavouriteNumber` mapping.

### Version Information
The contract is written with a pragma directive to ensure it's compiled with a Solidity compiler version greater than or equal to 0.6.0 but less than 0.9.0.

### Licensing
The contract is released under the GNU General Public License v3.0, as indicated by the SPDX-License-Identifier comment at the top of the file.

### Usage
1. **Storing a Favorite Number**: Call the `store` function with a `uint256` argument to store a favorite number.
2. **Retrieving the Favorite Number**: Call the `retrieve` function to get the stored favorite number.
3. **Adding a Person**: Call the `addPerson` function with a name (string) and a favorite number (uint256) to add a person’s information to the contract.
4. **Querying Information**: 
   - You can access the `people` array and the `nameToFavouriteNumber` mapping directly since they are public.
   - Use a person's index in the `people` array to retrieve their information.
   - Use a person's name as a key in the `nameToFavouriteNumber` mapping to get their favorite number.

### Conclusion
The `SimpleStorage` contract provides a basic example of how to interact with the Ethereum blockchain using Solidity. It demonstrates the use of various data types, functions, and solidity concepts, making it a great starting point for beginners looking to understand how smart contracts work.

********************************************************************************************************************************************************************************
**2.**
## StorageFactory Contract

The `StorageFactory` contract is a Solidity smart contract designed to interact with another contract, `SimpleStorage`. This contract demonstrates advanced Solidity concepts such as contract interaction, inheritance, and array manipulation.

### Features

#### 1. Inheritance
   - The `StorageFactory` contract inherits from `SimpleStorage`, allowing it to use all public and internal functions and state variables of `SimpleStorage`.
   
#### 2. Contract Interaction
   - **Creating SimpleStorage Contracts**: The `createSimpleStorageContract` function allows users to deploy a new `SimpleStorage` contract and store its address in an array.
   - **Interacting with SimpleStorage Contracts**: The `sfStore` and `sfGet` functions interact with specific `SimpleStorage` contracts from the array, demonstrating how one contract can interact with another.

#### 3. Array of Contracts
   - `simpleStorageArray`: A public dynamic array that holds the addresses of `SimpleStorage` contracts created by the `StorageFactory` contract.
   
#### 4. Functions
   - `createSimpleStorageContract()`: Deploys a new `SimpleStorage` contract and adds its address to the `simpleStorageArray`.
   - `sfStore(uint256 _simpleStorageIndex, uint256 _simpleStorageNumber)`: Stores a number in a specific `SimpleStorage` contract from the array.
   - `sfGet(uint256 _simpleStorageIndex)`: Retrieves the stored number from a specific `SimpleStorage` contract from the array.

### Version Information
The contract is written with a pragma directive to ensure it's compiled with a Solidity compiler version greater than or equal to 0.6.0 but less than 0.9.0.

### Licensing
The contract is released under the GNU General Public License v3.0, as indicated by the SPDX-License-Identifier comment at the top of the file.

### Usage
1. **Creating SimpleStorage Contracts**: Use the `createSimpleStorageContract` function to deploy new `SimpleStorage` contracts.
2. **Storing and Retrieving Numbers**: Use the `sfStore` function to store a number in a specific `SimpleStorage` contract, and `sfGet` to retrieve it.
3. **Interacting with SimpleStorage**: Since `StorageFactory` inherits from `SimpleStorage`, you can also directly call `store`, `retrieve`, and `addPerson` functions of the `SimpleStorage` contract.

### Conclusion
The `StorageFactory` contract provides a practical example of contract interaction, inheritance, and array manipulation in Solidity. It shows how to manage and interact with multiple contract instances, making it a useful reference for developers looking to understand advanced Solidity concepts and patterns.


**********************************************************************************************************************************************************************************

**3.**
# FundMe Smart Contract

## Overview
The FundMe smart contract is a crowdfunding application built on the Ethereum blockchain, enabling users to financially support the project by sending Ether (ETH). The contract ensures that the amount of ETH sent by each user meets a specified minimum requirement in USD, making use of Chainlink's price feed to fetch the current ETH/USD exchange rate.

## Key Features

### SafeMath for Arithmetic Operations
The contract employs `SafeMathChainlink` to perform safe arithmetic operations, safeguarding it from common vulnerabilities like overflow and underflow.

### Ownership Management
The address that deploys the contract is designated as the owner. Certain functionalities, such as withdrawing funds, are restricted to the owner, providing an additional layer of security and control.

### Minimum Funding Requirement
Users are required to send a minimum amount of ETH, determined by its equivalent value in USD. This ensures that all contributions meet the project's financial requirements.

### Real-Time ETH/USD Exchange Rate
The contract interacts with Chainlink’s AggregatorV3Interface to fetch the real-time exchange rate between ETH and USD, ensuring the minimum funding requirement is always up to date.

## Functions

### fund
Allows users to send ETH to the contract, provided that the USD equivalent meets or exceeds the minimum requirement. The sender’s address and amount sent are recorded.

### getVersion
Returns the version of the Chainlink price feed being used.

### getPrice
Fetches the current ETH price in USD.

### getConversionRate
Calculates the USD equivalent of a given amount of ETH.

### withdraw
Enables the owner to withdraw all funds from the contract and resets the funded amount for all contributors to zero.

## Modifiers

### onlyOwner
Ensures that certain functions can only be called by the owner of the contract.

## Constructor
Sets the contract's deployer as the owner.

## Usage in Decentralized Crowdfunding
This smart contract represents a fundamental building block for decentralized crowdfunding applications, ensuring transparency, security, and verifiability of transactions on the Ethereum blockchain.

**********************************************************************************************************************************************************************************
**So the first Three Exercises are done in Remix IDE, now as we gained some knowledge let's take it to the next step**
1. Download VS Code
2. Add extensions Python, Solidity
3. Install Python
**********************************************************************************************************************************************************************************

**4.** 
# Web3 py Simple Storage

In this exercise we will do the same SimpleStorage Contract that we did in the first exercise but in our local IDE.
Follow the steps:
1. create a dir using mkdir in your system as web3_py_simple_storage
2. Then create a file SimpleStorage.sol and copy the contract we used in the first exercise
3. Ok so now we have a folder with contract but how are we going to deploy it? so that's where we use python
4. Create a file called deploy.py
5. In remix if you notice every time we save it compiles automatically, so to compile here we need to install pip install py-solc-x
6. Doing so now if you observe in deploy.py file we use compiled_sol = compile_standard i.e. where we are declaring compiler-related info. If you just print(compiled_sol) and run python deploy.py, you will see a lot of low-level byte code.
7. So to deploy our contract we need bytecode, abi so if you follow my code in deploy.py you will see how it can be read in.
8. So now we need a blockchain where we can deploy our contract to check, In the remix we have Java VM accounts to test so here we need to use Ganache so download it, it will provide us with fake accounts with ethers in them which we will use as our local blockchain to test our smart contracts
9. After Downloading Ganache just click quickstart it will automatically create a local blockchain and give you accounts to play with
10. Install web3 using pip install web3
11. In deploy.py for connecting to ganache change the http provider with your own which is displayed on the top of the ganache, and edit the address and private key with your own from ganache
12. For safe use of private key use env variables
