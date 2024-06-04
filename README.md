# Mindset Labs DAO

## Introduction

Mindset Labs DAO is an online social initiative to create and manage a community revolving around tech education, specifically blockchain development, and open-source web3 products built with a profit sharing model.

The goal is to start by releasing a course for smart-contracts development along with a set of smart contracts to manage the most basic elements of a DAO. This is to be built with CosmWasm (rust-based smart contracts) and released to kick-start the community.

Other closely related initiatives such as the release of an NFT collection will accompany the DAO as some of the first community-led projects with many more to come in the future.

Success is to be measured by how many projects the community has released and earns income from. Earned income from projects is to be distributed among contributors, community members (NFT  holders) and the DAO treasury (staked).

In simple words, we must think of this as a social experiment running as a DAO. If it works, we can say that we were a part of a new social structure that may evolve into something bigger in the future.

We are workings towards the ultimate goal of being an education & product development network-state operating on-chain.



## Contracts

The contracts are to be built with CosmWasm, a rust-based smart contract platform. The contracts will be open-source and will be released under the MIT license.

There are 4 main contracts that are being developed:

### **Governance** 

This is the executive contract that will manage the DAO. It will have the ability to interact with the other contracts to ensure the smooth functioning of the DAO. The governance contract will be able to execute proposals, manage the treasury (payments, profit-sharing, etc..) and manage roles within the community via the _Membership_ contract. See ([contracts/governance](./contracts/governance/)) for more details.

**Key Functions:**
- **SetGovernancePolicy**: Defines or updates governance policies.
- **GetMemberDetails**: Retrieves details about a specific member, including roles and voting power.
- **ExecuteProposal**: Executes proposals that have been approved by the majority.


### **Membership**

This contract is a simple NFT contract that will manage access to the DAO. It will be used to manage roles within the DAO. The properties of the NFT will be used to determine the roles and access levels of each holder. See ([contracts/membership](./contracts/membership/)) for more details.

**Key Functions:**
- **MintNFT**: Mints a new membership NFT.
- **TransferNFT**: Transfers an NFT from one member to another.
- **BurnNFT**: Burns an NFT, effectively ending membership.
- **GetNFTDetails**: Retrieves details about a specific NFT, including its perks and status.
- **AssignRole**: Assigns specific roles (e.g., moderator, content creator) to members.
- **RevokeRole**: Revokes roles from members.


### **Treasury**

This contract will manage the funds of the DAO. It will be able to receive funds, send funds, and manage the profit-sharing model of the DAO. The treasury will be managed by the governance contract. See ([contracts/treasury](./contracts/treasury/)) for more details.

**Key Functions:**
- **DepositFunds**: Allows members to deposit funds into the treasury.
- **WithdrawFunds**: Enables authorized withdrawals from the treasury.
- **AllocateFunds**: Allocates funds for specific DAO initiatives based on approved proposals.
- **GetTreasuryBalance**: Returns the current balance of the treasury.
- **TrackTransactions**: Keeps a record of all transactions involving the treasury.
- **DistributeProfits**: Distributes profits to NFT holders based on predefined rules.
- **CalculateShare**: Calculates the share of profits for each NFT holder.
- **ClaimShare**: Allows members to claim their share of profits.
- **TrackEarnings**: Tracks earnings and distributions for transparency and auditing.


### **Democracy** 

This contract will manage the voting mechanism of the DAO. It will be used to create proposals and vote on them. The democracy contract will be managed by the governance contract. See ([contracts/democracy](./contracts/democracy/)) for more details.

**Key Functions:**
- **CreateProposal**: Allows members to create new proposals. Requires the NFT membership to be locked temporarily.
- **VoteOnProposal**: Facilitates the voting process, allowing members to cast their votes.
- **TrackVotes**: Records and tracks votes to ensure transparency and accountability.
- **GetProposalStatus**: Retrieves the current status of a proposal.