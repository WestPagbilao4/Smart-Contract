# ErrorHandlingExample Smart Contract
## Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The ErrorHandlingExample contract includes functions that utilize require(), assert(), and revert() statements to handle errors and validate conditions within the contract. This contract serves as a basic introduction to error handling in Solidity, providing a foundation for more complex projects in the future.
# Getting Started
## Executing the program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., ErrorHandlingExample.sol). Copy and paste the following code into the file:
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract ErrorHandlingExample {

    // State variable to store the owner's address
    address public owner;

    // State variable to store a value
    uint256 public value;

    // Constructor to set the owner of the contract
    constructor() {
        owner = msg.sender;
    }

    // Function to set a value with require statement
    function setValue(uint256 _value) public {
        // Ensure the sender is the owner
        require(msg.sender == owner, "Caller is not the owner");
        value = _value;
    }

    // Function to divide two numbers with assert statement
    function divide(uint256 a, uint256 b) public pure returns (uint256) {
        // Ensure denominator is not zero
        assert(b != 0);
        return a / b;
    }

    // Function to revert the transaction based on condition
    function revertExample(uint256 _value) public pure {
        // Revert if value is less than 100
        if (_value < 100) {
            revert("Value must be at least 100");
        }
    }
} 
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to ^0.8.0 (or another compatible version), and then click on the "Compile ErrorHandlingExample.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the ErrorHandlingExample contract from the dropdown menu, and then click on the "Deploy" button.

## Interacting with the Contract

- Once the contract is deployed, you can interact with it by calling the following functions:

- setValue(uint256 _value): Sets the value state variable. Only the owner can call this function. If the caller is not the owner, the transaction will revert with the message "Caller is not the owner".

- divide(uint256 a, uint256 b): Divides a by b and returns the result. If b is zero, the transaction will revert due to the assert(b != 0) statement.

- revertExample(uint256 _value): Reverts the transaction if _value is less than 100, with the message "Value must be at least 100".

# Authors
West Pagbilao
GitHub: @WestPagbilao4

# License
This project is licensed under the MIT License - see the LICENSE file for details.

