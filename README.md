Goal 2: 
Staking Contract:

Smart contract for a staking platform built on the Polygone TestChain. The contract allows users to deposit a specific token, stake it for a certain period of time, and earn rewards based on the staking duration. Let's break down the main components and how the contract works:
Interfaces and Libraries:

The ITRC20 interface represents the ERC-20 token standard functions that the staking contract interacts with.
The SafeMath library provides safe arithmetic operations to prevent overflows and underflows.
Contract Inheritance:

The Ownable contract serves as a base contract to manage ownership of the staking contract.
The Staking contract inherits from Ownable, indicating that it has owner-specific functions and modifiers.
Constructor:

The constructor initializes the staking contract with the address of the staking token (of type ITRC20).
It also initializes a mapping named allocation that associates staking durations (in days) with reward allocation percentages.

Struct and Mapping Definitions:

The userInfo struct holds various information about a user's staking activity.
The contract uses several mappings to keep track of user data, including deposited amounts, lockable days, deposit times, and more.
Events:

The Deposite_ event is emitted when a user makes a deposit.
Staking and Reward Mechanism

Users can stake a specified amount of tokens for a given number of lockable days using the farm function.
The contract calculates and accumulates rewards based on the allocation percentage and lockable days, updating user data accordingly.
The pendindRewards function calculates the rewards that are ready to be claimed by a user.
The harvest function allows users to claim their rewards. Rewards are either calculated based on the predefined allocation percentage or, if the lock-up period hasn't ended, they're calculated pro-rata.
Deduction percentages are applied to the staked amount in case users withdraw before the lock-up period ends.
Owner Functions:

The owner can change the deduction percentage and the time calculation unit.
The owner can withdraw excess tokens from the contract using emergencyWithdraw.
The owner can also withdraw excess BNB (if any) from the contract using emergencyWithdrawBNB.

User Information Queries:

The UserInformation function allows users to query their staking data, including deposited amounts, lockable days, and deposit times.
Modifiers:

The onlyOwner modifier restricts certain functions to be callable only by the owner of the contract.

Overall, this smart contract allows users to stake a specific token for various lockable periods and earn rewards based on the staking duration. It implements reward calculations, deduction percentages, and the ability for users to claim their rewards. The contract also provides emergency withdrawal functionality for the owner to manage the contract's assets.


Contract address: https://mumbai.polygonscan.com/address/0xeb210f2f39beb8e2c85326db9167a33b271b29c2 


