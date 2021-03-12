---
title: What is MakerDAO Crypto
tree_state: 🌱
---

You put in some crypto as collateral and you can create as much DAO as you want as long as it is less than 150% of the value of the collateral. This ensures that DAO is always backed up by real money.

If the value of your collateral drops below 150% of the DAI you have been loaned, your collateral is automatically liquidated. In the liquidation process, the value of your debt(DAI), the stability fee and the liquidation penalty are subtracted from your collateral value. And you receive the value of the leftover collateral.

### Stability of DAI
- If DAI is worth more than 1 dollar (maybe not quite a dollar because you need 150% collateral), you are financially incentivized to take out DAI via a lone because you can get it for cheaper than buying it on the open market. You would want to buy DAI on the market if DAI is worth less than approx 1 dollar.
- There is a stability fee which is like the interest you have to pay for receiving a loan. The stability fee must be paid every time pay back your debt. The fee is set by an algorithm to respond to the market. An increase in the stability fee results in a higher cost of borrowing for CDP users, thus dampening the DAI supply by making CDP usage less attractive. Conversely, a decrease in the stability fee (cost of borrowing) will incentivize the additional creation of DAI, acting as a policy tool to tweak supply growth.
- There is a MKR token that is used to cover unpaid debt. The MKR token gives its holders the rights to vote for risk parameters such as debt ceiling, liquidation ratio, stability fee, or liquidation penalty. When automatic liquidation fails so that there is less collateral backing the DAI than its worth, the DAI system generates more MKR tokens and sells them on the market to cover for the gap that was not covered by the collateral liquidation. This dilutes the MKR token, so holders of MKR are incentivized to keep the system stable. 

More details here:
https://medium.com/icovo/why-is-dai-stable-9a9fa84feca7


