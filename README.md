# Functions and Errors

This project is a smart contract that implements the require(), assert() and revert() statements.

## Description

In the context of smart contracts, errors are unanticipated or undesirable states or circumstances that could arise while a contract is being executed. For a smart contract to be dependable and secure, error handling is essential. Ethereum smart contracts are typically written in Solidity, a programming language that has error-handling features.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Here is an example code of my error handling:
```

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract Error {
    uint public balance;

    function deposit(uint _amount) public {
        // Use require() to check a condition
        require(_amount > 0, "Deposit amount must be greater than 0");

        // Update the balance
        balance += _amount;
    }

    function withdraw(uint _amount) public {
        // Use require() to check a condition
        require(_amount > 0 && _amount <= balance, "Invalid withdrawal amount");

        // Update the balance
        balance -= _amount;
    }

    function testAssert(uint _a, uint _b) public pure returns (uint) {
        // Use assert() to check an invariant
        assert(_a + _b >= _a);

        // Return the sum
        return _a + _b;
    }

    function testRevert() public pure {
        // Use revert() to revert the transaction
        revert("This transaction has been reverted");
    }
}


```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar and then click on the "Compile [file_name].sol" button. Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Under deployed contracts, you should see the token name, token abbreviation and current total supply of your choice.

To check if the code works as it should, you can deploy the contract by selecting the "Deploy & Run Transactions" tab from the left-hand sidebar once the code has been compiled. After choosing the "Error" contract from the drop-down menu, press the "Deploy" button.

Once the contract is deployed, you can interact with it by trying to deposit and withdraw by entering an amount on its tab and check the balances. 

Thank you!

## Authors

Aziel Samaniego

202011004@fit.edu.ph
