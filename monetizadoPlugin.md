# Monetizado Plugin - Ideathon Proposal

## Overview

The Monetizado plugin is an extension of the [Monetizado](https://github.com/Monetizado/monetizadojs) project, to be able to monetize using web3.js any type of content on web 2.0, such as news, blogs, audios, videos, documents and much more, in a simple way and without depending on more extensions.

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

#### `getProtectedContentsForCurrentUser()`

- **Description:** List all content protected by the content creator calling this method
- **Steps:**
  1. Gets the list of monetized items (including cost, name, and more).
 
#### `getProtectedContentByAddressAndId(creator, Id)`

- **Description:** Returns content protected by a specified content creator and Id
- **Steps:**
  1. Gets the monetized item (including cost, name, and more).

#### `payAccess(creator, Id)`

- **Description:** Pay for content protected by a specified content creator and Id
- **Steps:**
  1. Verify if the creator and Id exists in the contract (in the chain selected by web3.js).
  2. Call for the method and pay for the content, including the gas.
  3. Return a boolean if the payment was successful. 

#### `currentUserHasAccess(creator, Id)`

- **Description:** Verify if the user has access to the monetized content (paid for the content).
- **Steps:**
  1. Return a boolean if the user (Caller) paid for the content and has access.

#### `changeAccessCost(id, newCost)`

- **Description:** Change the cost of access to specific content. The user/caller must be the creator to be able to change the cost.
- **Steps:**
  1. Verify the id for the caller (creator) is registered as protected content in the selected chain.
  2. Change with a new cost (in wei).

#### `unprotectContent(id)`

- **Description:** Release the content (it is no longer protected for paying users only).
- **Steps:**
  1. Verify the id for the caller (creator) is registered as protected content in the selected chain.
  2. Release the protected content

#### `protectContent(id)`

- **Description:** Re-protect content (paying users only).
- **Steps:**
  1. Verify the id for the caller (creator) is registered as protected content in the selected chain.
  2. Re-protect the content

#### `withdrawMoneyFromContent(Id,amount)`

- **Description:** The content creator can withdraw money from their content
- **Steps:**
  1. Verify the id for the caller (creator) is registered as protected content in the selected chain.
  2. Content creator approve the transaction and receive the amount specified.
 
## Category

- [x] Project Plugin: [Monetizado](https://github.com/Monetizado)

## Use Cases

- [x] Other: For the creation and monetization of static and/or dynamic content (such as blogs, news, audios, videos, PDFs, and more) by integrating into any web page.

## Usage (Before & After Plugin)

Before the plugin, Web developers need to import several libraries and make sure they are implementing the most recent version of the Monetizado javascript library, and make sure they are on a valid network to use it. The library creates and uses a new javascript property on _window_, `monetizado`.

Now, all you have to do is implement the plugin and execute the different methods. It is not necessary to use the _window.monetizado_ property.

## Video

[Here is a demo how Monetizado works](https://www.youtube.com/watch?v=Bz0YMgmsfCo)

With the plugin, it would be the same process, simplifying the development for the frontend.
