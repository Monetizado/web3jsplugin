# Monetizado Plugin - Ideathon Proposal

## Overview

The Monetizado plugin is an extension of the [Monetizado](https://github.com/Monetizado/Contracts) project, to be able to monetize using web3.js any type of content on web 2.0, such as news, blogs, audios, videos, documents and much more, in a simple way and without depending on more extensions.

In addition, using the web3.js extension simplifies use for content creators without having to worry about smart contracts and different networks.

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

- [x] Other: For the creation and monetization of static and/or dynamic content (such as blogs, news, audios, videos, PDFs, and more) by integrating into any web page.

## Usage (Before & After Plugin)

Before the plugin, Web developers need to import several libraries and make sure they are implementing the most recent version of the Monetizado javascript library, and make sure they are on a valid network to use it. 

Now, all you have to do is implement the plugin and execute the different methods

## Video

[Here is a demo how Monetizado works](https://www.youtube.com/watch?v=Bz0YMgmsfCo)

With the plugin, it would be the same process, simplifying the development for the frontend.
