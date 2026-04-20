# Decentralized Voting DApp

A blockchain-based voting application built with Solidity and Next.js.
Users connect their MetaMask wallet and cast a YES or NO vote on a
poll question. The smart contract enforces one vote per wallet, emits
events for every action, and allows only the owner to close voting.
All votes are stored permanently and transparently on the Sepolia
blockchain — no central authority controls the results.

---

## Contract Summary

### State Variables

| Variable | Type | Description |
|---|---|---|
| owner | address | Wallet that deployed the contract |
| question | string | The poll question |
| yesVotes | uint256 | Total YES votes |
| noVotes | uint256 | Total NO votes |
| votingOpen | bool | Whether voting is active |
| hasVoted | mapping | Tracks who has already voted |

### Functions

| Function | Type | Description |
|---|---|---|
| castVote(bool) | Write | Cast a YES or NO vote |
| endVoting() | Write | Owner closes the poll |
| getResults() | Read | Returns current vote counts |
| getPollSummary() | Read | Returns full poll information |
| checkIfVoted(address) | Read | Checks if address has voted |

### Events

| Event | Description |
|---|---|
| VoteCast | Emitted every time a vote is cast |
| VotingEnded | Emitted when voting is closed with final result |

---

## How to Compile and Deploy

### Step 1 — Setup MetaMask
1. Install MetaMask from metamask.io
2. Create a wallet and save your 12 word seed phrase
3. Switch network to Sepolia testnet
4. Get free test ETH from:
   https://cloud.google.com/application/web3/faucet/ethereum/sepolia

### Step 2 — Compile in Remix
1. Go to remix.ethereum.org
2. Create a new file called Voting.sol
3. Paste the contract code
4. Click the Solidity Compiler tab
5. Select compiler version 0.8.0 or higher
6. Click Compile Voting.sol
7. Green tick means success

### Step 3 — Deploy to Sepolia
1. Click the Deploy and Run Transactions tab
2. Change Environment to Browser Extension
3. Connect MetaMask when prompted
4. Verify MetaMask shows Sepolia network
5. Type your poll question in the constructor field
6. Click Deploy
7. Confirm in MetaMask
8. Wait 15 to 30 seconds
9. Copy the contract address that appears

### Step 4 — Interact
1. In Remix under Deployed Contracts
2. Blue buttons = read functions (free)
3. Orange buttons = write functions (costs gas)
4. Click castVote and enter true for YES or false for NO
5. Confirm in MetaMask

---

## Testnet Used

**Sepolia Ethereum Testnet**
- Chain ID: 11155111
- Explorer: https://sepolia.etherscan.io

---

## Deployed Contract

**Contract Address:**
```
0xaCe31116996B0dfb724D10154F3cdCDB97c913D1
```

**Etherscan Contract Page:**
https://sepolia.etherscan.io/address/0xaCe31116996B0dfb724D10154F3cdCDB97c913D1

---

## Explorer Links

**Deployment Transaction:**
https://sepolia.etherscan.io/tx/0x3dee4cbee9e1b93a489bc5d01d0549db245f84fb69127da229c5ce3adac6bc91

**Vote Interaction Transaction:**
https://sepolia.etherscan.io/tx/0x4193d932110d863605ff4a9507a6148bdb3de529297664258d84b9d1d2f3328c

---

## Frontend

**Live DApp URL:**
https://voting-dapp-flax-two.vercel.app
**GitHub Repository:**
https://github.com/towurujesutofunmi/voting-dapp
---

## Demo Instructions

### What to show in class (5-7 minutes):

**Step 1 — Prove Deployment**
- Open Etherscan contract page
- Show contract address and creation transaction
- Show timestamp and deployer address

**Step 2 — Connect Wallet**
- Open live Vercel URL
- Click Connect MetaMask
- Show automatic switch to Sepolia
- Show wallet address appearing

**Step 3 — Show State Before**
- Point to Live Results
- YES 0 votes — NO 0 votes
- This is current blockchain state

**Step 4 — Send Transaction**
- Click YES button
- Show MetaMask confirmation popup
- Point out Sepolia network shown
- Click Confirm

**Step 5 — Show Confirmation**
- Wait 15 to 30 seconds
- Show vote count update
- YES now shows 1 vote 100 percent

**Step 6 — Verify on Etherscan**
- Open vote transaction on Etherscan
- Show tx hash, block number, gas used
- Click Logs tab
- Show VoteCast event with voter address

**Step 7 — End Voting**
- Click End Voting button
- Confirm in MetaMask
- Show VotingEnded event on Etherscan
- Show Voting Closed badge on website

---

## Tech Stack

| Tool | Purpose |
|---|---|
| Solidity | Smart contract language |
| Remix IDE | Contract development and deployment |
| MetaMask | Wallet and transaction signing |
| Sepolia | Ethereum test network |
| Etherscan | Blockchain explorer and verification |
| Next.js | Frontend framework |
| ethers.js | Blockchain connection library |
| GitHub | Code storage and version control |
| Vercel | Frontend hosting and deployment |

---

## Project Structure

```
voting-dapp/
├── app/
│   └── page.jsx        # Main frontend interface
├── contracts/
│   └── Voting.sol      # Smart contract
├── package.json        # Dependencies
├── tsconfig.json       # TypeScript config
└── README.md           # This file
```

---

## Requirements Met

- Smart contract with state variables that change via transactions
- At least two functions — one write and one read
- At least one event emitted and shown in demo
- Validation using require statements
- Deployed on Sepolia public testnet
- Contract address and explorer links provided
- State changing transaction demonstrated
- Frontend DApp with MetaMask connection
- Live public URL accessible to anyone