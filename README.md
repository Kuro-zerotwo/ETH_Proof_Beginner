# ETH Proof Beginners Assessment
## Description
The following Solidity program defines a smart contract named `MyToken`. It includes three public variables: `t_name` i.e. "NightFall" for the token's name, `t_abb` i.e. "NFL" for its abbreviation, and `total_supply` (initially 0) for the total number of tokens. The contract also features a `balances` mapping to track the token balances of different addresses. It includes a `mint` function to create new tokens and add them to a specified address, increasing the total supply, and a `burn` function to destroy tokens from a specified address, reducing the total supply, provided the address has sufficient tokens.

# Getting Started

### Installing
*No Installation Required

### Execution of Program

* To execute the program
1. Open in Remix IDE
2. Create a new file and paste the 'MyToken' contract code into the file.
3. Compile
4. Deploy
* Contract
```cpp
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;


/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public t_name = "NightFall";
    string public t_abb = "NFL";
    uint public total_supply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address add, uint val) public
    {
           total_supply += val;
           balances[add] += val;
    }

    // burn function
  function burntokens (address add, uint val) public
    {
           if (balances[add]>=val)
           {
           total_supply -= val;
           balances[add] -= val;
           }
    }
}
```
## Help
If you encounter any issues or have questions regarding the contract, please feel free to open an issue in this repository or contact the authors directly.

## Authors
* Anita Devi- https://github.com/Kuro-zerotwo
  
## License 
This project is licensed under the MIT License - see the LICENSE.md file for details.


