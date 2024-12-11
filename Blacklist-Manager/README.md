# Blacklist Manager Smart Contract

## Description

The Blacklist Manager is a Clarity smart contract designed for managing a sophisticated blacklist system on the Stacks blockchain. It allows authorized administrators to add and remove addresses from a blacklist, manage admin roles, handle appeals, and control various aspects of the blacklisting process.

## Features

- Add and remove addresses from the blacklist
- Assign blacklist levels and expiry times
- Manage multiple admin roles (contract admin, backup admin, and regular admins)
- Appeal system for blacklisted addresses
- Blacklist reasons and appeal tracking
- Temporary blacklisting with expiry times
- Contract activity toggle
- Prevent accidental STX transfers to the contract

## Contract Structure

The contract is structured with the following main components:

1. Constants for error codes
2. Data variables for contract state
3. Maps for storing blacklist data, admin status, and appeals
4. Read-only functions for querying contract state
5. Private helper functions
6. Public functions for contract interactions

## Functions Overview

### Read-Only Functions

- `is-address-blacklisted`: Check if an address is blacklisted
- `get-blacklist-details`: Get details of a blacklisted address
- `get-blacklist-reason-for-address`: Get the reason for blacklisting an address
- `get-total-blacklisted-address-count`: Get the total number of blacklisted addresses
- `is-admin`: Check if an address is an admin
- `get-appeal-status`: Get the status of an appeal for an address
- `get-contract-status`: Get the current status of the contract

### Public Functions

- `set-contract-admin`: Set a new contract admin
- `set-backup-admin`: Set a new backup admin
- `add-admin`: Add a new admin
- `remove-admin`: Remove an admin
- `add-address-to-blacklist`: Add an address to the blacklist
- `remove-address-from-blacklist`: Remove an address from the blacklist
- `submit-appeal`: Submit an appeal for a blacklisted address
- `process-appeal`: Process a submitted appeal
- `toggle-contract-status`: Toggle the active status of the contract
- `update-blacklist-expiry`: Update the expiry time for a blacklisted address

## Error Codes

- `ERR-NOT-AUTHORIZED (u100)`: User is not authorized to perform the action
- `ERR-ALREADY-BLACKLISTED (u101)`: Address is already blacklisted
- `ERR-NOT-BLACKLISTED (u102)`: Address is not blacklisted
- `ERR-INVALID-ARGUMENT (u103)`: Invalid argument provided
- `ERR-BATCH-OPERATION-FAILED (u104)`: Batch operation failed
- `ERR-ADMIN-ONLY (u105)`: Action restricted to admins only
- `ERR-CANNOT-BLACKLIST-ADMIN (u106)`: Cannot blacklist an admin
- `ERR-INVALID-TIME (u107)`: Invalid time provided
- `ERR-EXPIRED-BLACKLIST (u108)`: Blacklist entry has expired

## Security Considerations

1. Only authorized admins can perform sensitive operations.
2. The contract prevents accidental STX transfers.
3. Admins cannot be blacklisted to prevent lockouts.
4. Expiry times are used to implement temporary blacklisting.
5. The contract admin and backup admin roles provide additional security.


## Contributing

Contributions to improve the Enhanced Blacklist Manager are welcome. Please follow these steps:

1. Fork the repository
2. Create a new branch for your feature
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request