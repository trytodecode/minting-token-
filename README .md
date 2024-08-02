# Mint Token
we will write smart contract and perform mint trasfer and burn 

## Description

this is the project created to demonstrate the use of smart contract and create our own ERC20 token and we have to perform minting function and have to interact using the contract we have sucessfuly compiled .

## Getting Started

### Installing

* to deploy this code you need to have remix or any IDE.
* need compiler for solidity 
* required version of solidity compiler is (version ^0.8.20)

### Executing program

*to deploy this block of code you need an IDE of  solidity
* after that copy paste the given block of code in your IDE
* then set compiler to version (0.8.20)
* in code section we have imported the openzepline and hadhart .
* then in deploy section paste the address of your own account.
* after that you will observe that contract is deployed and we re ready to interact 
* now you can perform opertion of the contract 


pragma solidity ^0.8.20;

import "hardhat/console.sol";
import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol"; // for Burn
import "@openzeppelin/contracts/access/Ownable.sol";
import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Permit.sol";

contract MyToken is ERC20, ERC20Burnable, Ownable, ERC20Permit {
    constructor(address initialOwner)
        ERC20("MyToken", "TK")
        Ownable(initialOwner)
        ERC20Permit("MyToken")
    {}

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public override {
        _burn(_msgSender(), amount);
    }

    function transfer(address from, address to, uint256 amount) external {
        _transfer(from, to, amount);
    }
}

## Help
* make sure your IDE is for solidity 

* make sure you safe search in brave browser is off 

* need to write address in deploy section or you will stuck there .

* make sure your compiler is set to version (0.8.20) otherwise error will throw

## Authors
kumar sanjeev 
https://www.linkedin.com/in/kumar-sanjeev-150965230/


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
