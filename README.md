# ERC20 Token Contract

This repository contains an ERC20 token implementation in Solidity. The token contract follows the ERC20 standard and includes basic functionalities such as transfer, approve, mint, and burn.

## Contract Overview

The `ERC20` contract implements the following functionalities:

- **Transfer:** Transfer tokens from one account to another.
- **Approve:** Approve another address to spend tokens on behalf of the token owner.
- **Transfer From:** Allows approved addresses to transfer tokens on behalf of another address.
- **Mint:** Mint new tokens (admin only).
- **Burn:** Burn tokens from the caller's account.

## Features

- Token Name: `Test`
- Token Symbol: `TST`
- Decimal Places: `0`
- Administrator: The account that deploys the contract is the admin and can mint tokens.

## Contract Functions

### 1. `transfer(address recipient, uint amount) external returns (bool)`
Transfers a specific `amount` of tokens to the `recipient` address.

### 2. `approve(address spender, uint amount) external returns (bool)`
Allows a `spender` to spend a specific `amount` of tokens on behalf of the message sender.

### 3. `transferFrom(address sender, address recipient, uint amount) external returns (bool)`
Transfers `amount` tokens from the `sender` to the `recipient` using the allowance mechanism.

### 4. `mint(uint amount) external`
Mints new tokens and increases the total supply. Only the admin can call this function.

### 5. `burn(uint amount) external`
Burns tokens from the caller's balance, reducing the total supply.

## Events

- **Transfer:** Emitted when tokens are transferred, including zero address for minting and burning.
- **Approval:** Emitted when an allowance is set by calling the `approve` function.

## Usage

### Deploy the Contract

You can deploy this contract on any Ethereum-compatible blockchain network. The `admin` who deploys the contract will be the one with the authority to mint new tokens.

### Mint Tokens

Only the contract admin can mint tokens by calling the `mint` function:

```solidity
mint(uint amount);
