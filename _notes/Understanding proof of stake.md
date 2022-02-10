---
title: Understanding proof of stake
tree_state: 🌱
---

## Details of Normal Blockchain and Proof of Stake
1. Individual transactions are sent to a subset of the network (I think)
2. Each individual transaction must contain a hashed version of the private key that's sending the money and the public key of the recipient.
3. There is a global state of the blockchain that the validators know of
4. The longest chain of transactions (I think it might be the largest amount of staking recorded in a blockchain to measure the longest chain) is recognized as the true state.
5. Validators are penalized and lose money if they validate a fork (a separate state of transaction history) that is then overturned or doesn't make it into the global state

## Potential Problems with Proof of Stake
Let's say most nodes have a notion of the global state at the current time. Then some bad actor validator creates a fork into the future with a bunch of transactions giving themselves money. How can we prevent this?
- If the fork projects transactions really far into the future, then other good validators will be inclined not to believe this fork and won't validate it to be added into the network. A random set of validators is used to check a proposed change/addition to the blockchain, so these probably won't be friends of the bad actor. 
- Also, the bad actor will be punished for suggesting this change if it isn't accepted, which disincentivizes them from suggesting it in the first place.
Suppose some bad actor validator creates a bunch of different forks that aren't that far into the future and disseminates them into the network. How can we stop this bad behavior?
- The bad actor will probably lose money since only one of these forks can be used, but let's say they include information giving them a bunch of money, so this is still a problem.
- For 1 of the forks to be accepted, they must spread out all over the network and have more validators merging them than a different state of the blockchain that is most likely spreading throughout the network simultaneously. Apparently, if 2/3 of the validators are not malicious and accept the majority ruling for the state of the blockchain, then this is not a threat (see Byzantine Fault Tolerance).