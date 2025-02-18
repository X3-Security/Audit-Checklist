### **✅ Audit Checklist: Profitable User Withdraws All Collateral Removing Liquidation Incentive**  

### **1️⃣ Can Users Withdraw Too Much Collateral?**  
🔲 **Does the protocol allow users to withdraw collateral based on unrealized PNL?**  
🔲 **Is there a minimum collateral requirement that must remain in the account?**  
🔲 **Does the protocol discount unrealized PNL when calculating withdrawable collateral?**  
🔲 **Can users withdraw collateral while still having open leveraged positions?**  
🔲 **Are there any restrictions preventing users from withdrawing if it affects liquidation conditions?**  

---

### **2️⃣ Will Liquidation Work If the User Withdraws All Their Collateral?**  
🔲 **Does liquidation rely only on deposited collateral, or can PNL be seized?**  
🔲 **What happens if a user’s collateral is fully withdrawn before liquidation?**  
🔲 **Does liquidation fail if there is no collateral left to seize?**  
🔲 **Are liquidators compensated in some way even if the user has no remaining collateral?**  
🔲 **Is there a mechanism to block withdrawals when a position is close to liquidation?**  

---

### **3️⃣ Can Attackers Exploit This to Avoid Liquidation?**  
🔲 **Can a user withdraw all collateral when in profit and later become unliquidatable?**  
🔲 **Can a user open multiple small positions, withdraw collateral, and leave unliquidatable positions?**  
🔲 **Can a whale manipulate prices, withdraw collateral, and leave the protocol with bad debt?**  
🔲 **Does the protocol account for sudden price reversals after large collateral withdrawals?**  
🔲 **Are there ways to delay or block liquidations by abusing collateral withdrawal rules?**  

---

### **4️⃣ Does the Protocol Adjust Liquidation Based on PNL and Collateral?**  
🔲 **Is there a proper calculation to prevent collateral withdrawals based on risk exposure?**  
🔲 **Does the liquidation mechanism consider unrealized PNL when determining liquidation conditions?**  
🔲 **Are liquidation fees adjusted dynamically to incentivize liquidators?**  
🔲 **Can the protocol seize PNL instead of just collateral if a user’s balance is too low?**  
🔲 **Are emergency shutdown mechanisms in place for extreme market volatility?**  

---

### **5️⃣ Mitigation Strategies & Fixes to Look For**  
✅ **Ensure a minimum collateral amount is always required for open positions.**  
✅ **Prevent collateral withdrawals if it would bring a position close to liquidation.**  
✅ **Use weighted PNL instead of full unrealized PNL when calculating collateral.**  
✅ **Allow liquidators to seize a portion of unrealized PNL if no collateral is left.**  
✅ **Require users to maintain an additional buffer margin before allowing withdrawals.**  

---
