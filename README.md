# project-solidity-assessment-metacraft


A simple Solidity smart contract that creates a custom token called META (abbreviation MTA). This contract implements minting and burning functionality, allowing users to increase or decrease the token supply.

## Description

This project defines a basic ERC-20-like token smart contract on the Ethereum blockchain. The smart contract stores the token's details, including the token name, abbreviation, and total supply. It also includes a minting function that allows tokens to be created and a burn function to destroy tokens. The balancesOf mapping tracks the balance of each address that holds the token.
## Getting Started

### Executing program

To run this program, you can use Remix Etherium IDE, an online Solidity IDE. To get started, go to the Remix website at (https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.26+commit.8a97fa7a.js)

Set up all configuration.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar.

License and Version Declaration
```solidity

pragma solidity ^0.8.18;
```

Contract Declaration and Public Variables
```solidity
contract MyToken {
    // Public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
```

Mapping for Balances : This line declares a mapping called balancesOf. It is a key-value pair where the key is an Ethereum address (address) and the value is a uint (unsigned integer) representing the balance of tokens that the address holds.
```solidity
    // Mapping variable here
    mapping(address => uint) public balancesOf;
```
Mint Function: This declares a public function called mint that allows anyone to mint (create) new tokens.
```solidity
    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balancesOf[_address] += _value;
    }
```
Burn Function
```solidity
    // Burn function
    function burn(address _address, uint _value) public {
        require(balancesOf[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balancesOf[_address] -= _value;
    }
}
```


The contract stores basic information about a custom token, such as its name, abbreviation, and total supply.
Users can mint tokens by calling the mint function, which increases both the total supply and the balance of a specific address.
Users can burn tokens by calling the burn function, which decreases the total supply and the balance of a specific address, provided they have enough tokens to burn.
This contract is a simple implementation of a token with minting and burning features, and it can be used to manage tokens on the Ethereum blockchain or any EVM-compatible blockchain.

## Authors

Tushar Srivastav



## License

This project is licensed under the MIT License - see the LICENSE.md file for details
