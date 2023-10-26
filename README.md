# SolidityLearning-Examples
In this repository, you should be able to learn solidity coding for smart contracts from basic to advanced level use of concepts

**Table of Contents**

**1.** SimpleStorage Contract

**2.** StorageFactory Contract

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
