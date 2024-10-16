# RatTax Coin (xdd)

## Overview

This is a simple Ethereum-based smart contract that defines a custom token named "RatTax" with the abbreviation "xdd". The contract allows minting and burning of tokens, and keeps track of token balances associated with user addresses. 

## Contract Features

### 1. Public Variables:
   - `tokenName`: Stores the name of the token ("RatTax").
   - `tokenAbbrv`: Stores the abbreviation of the token ("xdd").
   - `totalSupply`: Stores the total supply of the token, initially set to `0`.

### 2. Balances Mapping:
   - A mapping `balances` is used to store the token balances of each address. 
   - Format: `mapping(address => uint)`, where each address is associated with a `uint` value representing its token balance.

### 3. Mint Function:
   - `mint(address _address, uint _value)`: This function increases the total supply of tokens and adds the minted tokens to the balance of the provided `_address`.
   - **Parameters**:
     - `_address`: The address where tokens will be minted.
     - `_value`: The number of tokens to mint.
   - **Operation**:
     - Increases the total supply by `_value`.
     - Adds the `_value` to the balance of `_address`.

### 4. Burn Function:
   - `burn(address _address, uint _value)`: This function decreases the total supply of tokens and deducts the specified amount from the balance of the provided `_address`, if the balance is sufficient.
   - **Parameters**:
     - `_address`: The address from which tokens will be burned.
     - `_value`: The number of tokens to burn.
   - **Operation**:
     - Checks if the balance of `_address` is greater than or equal to `_value`.
     - If true, decreases the total supply by `_value` and deducts the `_value` from the balance of `_address`.

## Usage

### Minting Tokens
To mint new tokens, call the `mint` function with the desired address and amount:
```solidity
mint(address _address, uint _value);
```

### Burning Tokens
To burn tokens, call the `burn` function with the desired address and amount:
```solidity
burn(address _address, uint _value);
```
Ensure the `_address` has enough tokens in its balance to burn the specified amount.

## License

This contract is licensed under the MIT License.
