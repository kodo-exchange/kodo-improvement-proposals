# How to Use Kodo's Multisig

Kodo's multisig wallet is deployed at [0xB020af366819E68eCbD8ed5EC345FD85D7b1D6B2](https://taikoscan.io/address/0xB020af366819E68eCbD8ed5EC345FD85D7b1D6B2) and uses code from the 0x project, available [here](https://github.com/kodo-exchange/contracts/tree/main/contracts/multisig).

## Prerequisites

- You must be one of the multisig wallet holders.
- Ensure you have enough ETH in your wallet to cover transaction gas fees.

## How to Use It with taikoscan.io

### 1. Submit a Transaction

Transactions must be submitted by one of the multisig holders.

1. Visit [taikoscan.io write contract page](https://taikoscan.io/address/0xB020af366819E68eCbD8ed5EC345FD85D7b1D6B2#writeContract).
2. Fill in the `submitTransaction` section with the following information:
   - `destination`: The contract address the multisig will interact with, or the EOA (Externally Owned Account) address for transfers.
   - `value`: Set to 0 if interacting with a contract, or specify the amount of ETH to transfer.
   - `data`: The encoded data of the function and parameters starting with 0x, or just 0x if there is no contract call.

For encoding `data`, tools like [ABI Hashex](https://abi.hashex.org/) can be used to encode functions and parameters.

### 2. Confirm Transaction

Only multisig holders can confirm transactions.

1. Go to [taikoscan.io write contract page](https://taikoscan.io/address/0xB020af366819E68eCbD8ed5EC345FD85D7b1D6B2#writeContract).
2. In the `confirmTransaction` section, enter the `transactionId` returned after submission.

### 3. Execute Transaction

Anyone can execute the transaction as long as the confirmation requirement is met.

1. Visit [taikoscan.io write contract page](https://taikoscan.io/address/0xB020af366819E68eCbD8ed5EC345FD85D7b1D6B2#writeContract).
2. In the `executeTransaction` section, enter the `transactionId` returned after submission.

Note that sometimes execution may fail because MetaMask cannot correctly estimate the gas limit. Please increase the gas limit to ensure correct execution.