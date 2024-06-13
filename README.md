// SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract MyToken {

    // Public variables here
    string public tokenName = "META";
    string public tokenSymbol = "MTA"; // Corrected typo (Symbol instead of Abrrv)
    uint public totalSupply = 0;

    // Mapping to store token balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _to, uint _value) public { // Corrected parameter name (_to)
        totalSupply += _value;
        balances[_to] += _value;
    }

    // Burn function
    function burn(address _from, uint _value) public { // Function renamed to burn
        require(balances[_from] >= _value, "Insufficient balance for burning"); // Added require statement
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
