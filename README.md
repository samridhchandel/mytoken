# ETH Proof  beginner  Assignment 

A simple overview of use/purpose.

## Description

An in-depth paragraph about your project and overview of use.

## Getting Started

### Installing

*No Installation Needed 

### Executing program

* How to run the program
1. Open In Remix 
2. Compile
3. Deploy
* Contract
```cpp
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to accounts (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/
contract MyToken{

// public variables here
    string public tokenName = "Samridh";
    string public tokenAbbrv = "GT";
    uint public totalSupply = 0;

// mapping variable here
    mapping(address => uint) public rulers;

//mint function
    function mintToken(address _address,uint _value)public{
        totalSupply += _value;
        rulers[_address] += _value;
    }
// burn function
    function burnToken (address _address, uint _value)public{
        if(rulers[_address]>= _value){
            totalSupply -= _value;
            rulers[_address] -= _value;
        }
    }
}
```
