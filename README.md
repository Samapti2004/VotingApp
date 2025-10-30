# VotingApp
A simple decentralized voting application built with Solidity and deployed on the Celo Blockchain (Sepolia Testnet).
This project demonstrates how blockchain can ensure fair, transparent, and tamper-proof voting.

<img width="1887" height="959" alt="Screenshot 2025-10-29 140324" src="https://github.com/user-attachments/assets/a1d917b6-c47e-4050-a9ed-05e4e4ff0968" />

## 📜Project Description

A simple decentralized voting application built with Solidity and deployed on the Celo Blockchain (Sepolia Testnet).
This smart contract allows the owner to add candidates and users to vote only once.
All votes are stored on-chain for transparency and security.

## ⚙️What It Does

- Owner deploys the voting contract

- Owner adds candidates

- Anyone can vote (one vote per address)

- Voting can be closed by the owner

- Results can be viewed on-chain

## 🌟 Features
- ✅ Beginner-friendly Solidity design
- ✅ One-vote-per-user rule enforced
- ✅ Voting open/close controlled by owner
- ✅ Full transparency on blockchain
- ✅ View candidate details + vote counts


## 📄 Smart Contract

- **Language:** Solidity ^0.8.20  
- **Framework:** Remix / Hardhat compatible  
- **Network:** Celo Sepolia Testnet  
- **Deployed Transaction:**  

👉 [View on Blockscout](https://celo-sepolia.blockscout.com/address/0x2BE4b0F75064ebCD0F4F5342CA15F3Fe74b447A7)

## 💻 Smart Contract Code
```bash
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

/*
 * 🗳 Simple Voting DApp — Beginner Friendly Solidity Project
 * ------------------------------------------------------------
 * This contract allows users to vote for candidates.
 * The owner adds candidates, and anyone can vote once.
 */

contract VotingApp {

    address public owner;

    struct Candidate {
        string name;
        uint256 voteCount;
    }

    Candidate[] public candidates;

    mapping(address => bool) public hasVoted;

    event Voted(address indexed voter, uint256 candidateIndex);
    event CandidateAdded(string name);

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can perform this action");
        _;
    }

    function addCandidate(string memory _name) public onlyOwner {
        candidates.push(Candidate({name: _name, voteCount: 0}));
        emit CandidateAdded(_name);
    }

    function vote(uint256 candidateIndex) public {
        require(!hasVoted[msg.sender], "You have already voted!");
        require(candidateIndex < candidates.length, "Invalid candidate index");

        hasVoted[msg.sender] = true;
        candidates[candidateIndex].voteCount += 1;

        emit Voted(msg.sender, candidateIndex);
    }

    function getTotalCandidates() public view returns (uint256) {
        return candidates.length;
    }

    function getCandidate(uint256 index) public view returns (string memory, uint256) {
        require(index < candidates.length, "Invalid index");
        Candidate memory c = candidates[index];
        return (c.name, c.voteCount);
    }
}
```

## 🚀 How to Run Locally
**1️⃣ Clone the repository**
```bash
git clone https://github.com/your-username/VotingApp.git
cd VotingApp
```
**2️⃣Open Remix IDE**
-Visit Remix IDE
-Paste your smart contract code inside a new file (VotingApp.sol)

**3️⃣Compile & Deploy**

- Select Solidity Compiler → version 0.8.20
- Deploy using Injected Web3 to connect your Celo wallet

**4️⃣ Interact with the Contract**
- Call vote() with the candidate index.
- Use getCandidate() to view results.
## 🧩 Future Enhancements
- 🖥️ Build a React front-end with Celo Composer or Ethers.js
- 🧾 Add voter registration and candidate management
- 📊 Display live voting stats on UI
- 🔐 Integrate identity verification (optional)
## 🙌 Acknowledgments
- **Celo Blockchain-** for providing eco-friendly infrastructure
- **Remix IDE-** for easy smart contract testing
- **Blockscout-** for transparent transaction viewing
> 💡 Pro Tip: Start small — experiment, break things, and learn how decentralized apps work under the hood.

🧠 Made with ❤️ by **Samapti2004**
