# EthProofAssesment
Overview
This repository contains a Solidity smart contract for a custom token named "INDIA" with the abbreviation "IN". The contract includes functionality for minting and burning tokens, as well as tracking balances of addresses.

Requirements
Solidity ^0.8.0
Remix IDE (recommended for deployment and testing)
Contract Details
Public Variables
tokenName: The name of the token ("INDIA").
tokenAbbrv: The abbreviation of the token ("IN").
totalSupply: The total supply of tokens in existence.
Mapping
balances: A mapping of addresses to their respective token balances.
Functions
mint(address _address, uint _value): Increases the total supply and the balance of the specified address by the given value.
burn(address _address, uint _value): Decreases the total supply and the balance of the specified address by the given value, ensuring the address has sufficient balance.
