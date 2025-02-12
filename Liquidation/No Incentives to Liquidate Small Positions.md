### **✅ Audit Checklist: No Incentive to Liquidate Small Positions**

#### **1️⃣ Can Users Create Small Positions?**  
🔲 **Is there a minimum collateral requirement?** (Check `deposit()`, `createVault()`, `mintStable()`)  
🔲 **Is there a minimum borrow amount?** (Check `borrow()`, `drawDebt()`)  
🔲 **Can users withdraw collateral to bypass limits?** (Check `withdraw()`, `exitVault()`)  
🔲 **Can users open multiple small vaults/loans per address?**  

#### **2️⃣ Will Small Positions Get Liquidated?**  
🔲 **Is there a minimum liquidation threshold?** (Check `liquidate()`, `closePosition()`)  
🔲 **Are liquidators incentivized enough to act?** (Review reward calculations in liquidation functions)  
🔲 **Does liquidation require additional gas-heavy actions?** (E.g., staking before liquidating)  
🔲 **Are batch liquidations supported to offset gas costs?** (Look for `batchLiquidate()`, `multiLiquidate()`)  
🔲 **Is liquidation permissionless, or does it require special roles?** (Look for `onlyWhitelisted` restrictions)  

#### **3️⃣ Profitability Analysis: Are Small Positions Worth Liquidating?**  
🔲 **Does the liquidation reward cover gas fees?** (Simulate gas costs vs. profit)  
🔲 **Does liquidation incentive scale with position size?** (Check if small positions get a liquidation bonus)  
🔲 **Can attackers spam the system with many small, unliquidatable positions?** (Fuzz test multiple small positions)  
🔲 **Does the protocol adjust liquidation fees based on gas price fluctuations?**  
🔲 **Are emergency liquidation mechanisms in place for extreme market conditions?**  

#### **4️⃣ Exploitation Checks: Can an Attacker Use This Against the Protocol?**  
🔲 **Can an attacker short the protocol token while flooding it with small positions?**  
🔲 **Can a whale create thousands of unliquidatable vaults?**  
🔲 **Are there mechanisms to remove bad debt from the protocol?** (Look for `buyBadDebt()`, `treasuryCoverDebt()`)  

#### **📌 Recommended Fixes for This Issue**  
✅ **Set a Minimum Collateral Requirement**  
✅ **Enforce a Minimum Borrow Amount**  
✅ **Increase Liquidation Incentives for Small Positions**  
✅ **Enable Batch Liquidations to Reduce Gas Costs**  
✅ **Make Liquidation Permissionless (Allow Anyone to Liquidate)**  

---