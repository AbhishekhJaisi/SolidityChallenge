# SolidityChallenge


//SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
 
 
contract MyToken {
 
    string public tokenName = "Roshan";
    string public tokenAb = "Hello";
    uint public totalSupply = 0;
 
 
    // variable mapping
    mapping(address=>uint) public tokenHolders;
 
 
    // + mint fun
    function mint(address _address, uint _value) public{
        totalSupply+=_value;
        tokenHolders[_address] += _value;
    }
 
 
    // - burn fun
    function burn(address _address, uint _value) public{
        require(tokenHolders[_address] > _value, "funds not available");
        totalSupply-=_value;
        tokenHolders[_address] -= _value;
    }
 
}
