# VotingApp
A simple decentralized voting application built with Solidity and deployed on the Celo Blockchain (Sepolia Testnet).
This project demonstrates how blockchain can ensure fair, transparent, and tamper-proof voting.

<img width="1887" height="959" alt="Screenshot 2025-10-29 140324" src="https://github.com/user-attachments/assets/a1d917b6-c47e-4050-a9ed-05e4e4ff0968" />

📜 Project Description
Voting DApp allows users to vote for their favorite candidates in a transparent way.
Each voter can vote only once, and every vote is recorded on-chain, making it immutable and verifiable.

The project is designed for beginners learning Solidity and Celo smart contract development.

⚙️ What It Does
The contract owner deploys the smart contract with a list of candidates.
Users connect their wallet and vote for their preferred candidate.
Each address can vote only once.
The owner can close the voting when it’s over.
Results can be viewed directly from the blockchain.
🌟 Features
🧠 Simple & Beginner-Friendly: Easy to understand Solidity structure.
🔒 One-Vote Rule: Each wallet address can only vote once.
⛓️ On-Chain Transparency: All votes are publicly verifiable.
🪙 Deployed on Celo Sepolia: Uses Celo’s testnet for a smooth developer experience.
👨‍💼 Owner Privileges: Only the contract deployer can end the voting phase.
📄 Smart Contract
Language: Solidity ^0.8.20
Framework: Remix / Hardhat compatible
Network: Celo Sepolia Testnet
Deployed Transaction:
👉 View on Blockscout
💻 Smart Contract Code
//paste your code
🚀 How to Run Locally
Clone the repository

git clone https://github.com/your-username/XXX.git
cd XXX
Open Remix IDE

Visit Remix IDE
Paste your smart contract code inside a new file (VotingDApp.sol)
Compile & Deploy

Select Solidity Compiler → version 0.8.20
Deploy using Injected Web3 to connect your Celo wallet
Interact with the Contract

Call vote() with the candidate index.
Use getCandidate() to view results.
🧩 Future Enhancements
🖥️ Build a React front-end with Celo Composer or Ethers.js
🧾 Add voter registration and candidate management
📊 Display live voting stats on UI
🔐 Integrate identity verification (optional)
🙌 Acknowledgments
Celo Blockchain for providing eco-friendly infrastructure
Remix IDE for easy smart contract testing
Blockscout for transparent transaction viewing
💡 Pro Tip: Start small — experiment, break things, and learn how decentralized apps work under the hood.

🧠 Made with ❤️ by [Your Name / XXX]
