# Monetizado Plugin - Ideathon Proposal

## Overview

[Provide a brief overview of the plugin and its purpose]

- How does the project works?
- What problem the plugin solves?
- How does it improve the DevEx or project functionality?

## Features

### Storage

1. **ABI for the [Monetizado Contract](https://github.com/Monetizado/Contracts/tree/main/ABI)**: To maintain and store the ABI and [contract](https://github.com/Monetizado/Contracts/blob/main/v1/Monetizadov1.sol) for use in the plugin.
2. **Monetizado addresses**: [Monetizado addresses](https://github.com/Monetizado/Contracts/tree/main?tab=readme-ov-file#contract-ids) deployed in different EVM networks.

### Functions

#### `addProtectedContent(name, accessCost)`

- **Description:** Allows the creation of an object that will be monetized
- **Steps:**
  1. Select a name and cost (in wei) for the item that should be monetized.
  2. Gets the wallet ID of the creator (the user who is executing the method).
  3. Execute the `addProtectedContent(string memory name, uint256 accessCost)` method in the contract.
  4. Return a sequential ID for the contract (from zero), associated with the creator.

[Add more functions as needed]

## Category

- [x] Project Plugin: [Monetizado](https://github.com/Monetizado)

## Use Cases

- [x] Other: 

## Usage (Before & After Plugin)

Before the plugin, Web developers need to import several libraries and make sure they are implementing the most recent version of the Monetizado javascript library, and make sure they are on a valid network to use it. 
Now, all you have to do is implement the plugin and execute the different methods

## Mandatory

[Diagram or video explaning the process/flow of the plugin]
