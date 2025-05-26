# 🪙 SoulMintToken (SMT)

**SoulMintToken (SMT)** is a customizable, mintable, and burnable ERC-20 token smart contract built using OpenZeppelin libraries. It is designed for applications like loyalty points, reward systems, private token economies, and governance models.

---

## 🔍 Overview

SoulMintToken enables the **owner** to mint new tokens while allowing **any user** to burn (destroy) their own tokens, effectively reducing the total supply. This functionality is commonly used in deflationary tokenomics or utility-based token ecosystems.

---

## ⚙️ Token Details

| Property        | Value            |
|----------------|------------------|
| **Name**       | SoulMintToken    |
| **Symbol**     | SMT              |
| **Decimals**   | 18               |
| **Standard**   | ERC-20           |
| **License**    | MIT              |

---

## Contract Address:	0x348477a5117b3e0ad47a7a22f2e64e4b3523d673

## 📄 Smart Contract Code

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract SoulMintToken is ERC20, Ownable {
    constructor(uint256 initialSupply) ERC20("SoulMintToken", "SMT") Ownable(msg.sender) {
        _mint(msg.sender, initialSupply * 10 ** decimals());
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount * 10 ** decimals());
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount * 10 ** decimals());
    }
}

![image](https://github.com/user-attachments/assets/ff27e7c8-0078-4488-ad71-e8256f4da89a)
