### **📝 Checklist: Partial Liquidation Vulnerabilities in Smart Contracts**  

#### **🔍 Why Check for Partial Liquidation Issues?**  
Partial liquidations can be **exploited by liquidators** to **avoid covering bad debt**, leaving the protocol with financial losses. Ensuring proper handling of partial liquidations prevents **accumulating bad debt** and maintains the protocol’s solvency.

---

### **✅ 1️⃣ General Checks for Partial Liquidation**
- [ ] **Does the contract allow partial liquidation?**
- [ ] **If yes, does it ensure that a proportional share of bad debt is covered during partial liquidations?**
- [ ] **Are partial liquidations restricted if they would leave an "unreasonably small" remaining position?**
- [ ] **Can liquidators game the system by liquidating just enough to avoid covering bad debt?**
- [ ] **Are there protections against repeated partial liquidations to delay full liquidation?**
- [ ] **Does the contract differentiate between full and partial liquidation logic?**
- [ ] **Is there a clear incentive for liquidators to close full positions rather than only partial ones?**

---

### **🛠 2️⃣ Checking for Bad Debt Accumulation Risks**
- [ ] **Does the protocol enforce a check that liquidators must cover a proportional share of bad debt even for partial liquidations?**
- [ ] **Is there a mechanism (like an insurance fund) to absorb bad debt if liquidators fail to cover it?**
- [ ] **Can a position be liquidated multiple times without resolving its negative margin?**
- [ ] **Does the contract have safeguards against users deliberately undercollateralizing to create unprofitable liquidations?**

---

### **💰 3️⃣ Checking Margin and Collateral Handling**
- [ ] **Does the liquidation function properly update the user’s margin and debt after partial liquidation?**
- [ ] **Does the protocol properly track the remaining collateral after a partial liquidation?**
- [ ] **If a position is still undercollateralized after a partial liquidation, does the protocol trigger further liquidation or mitigation measures?**
- [ ] **Are liquidators prevented from draining all collateral while leaving an open, insolvent position?**
- [ ] **Does the protocol ensure that withdrawals are blocked if the margin falls below a safe threshold?**

---

### **⚠️ 4️⃣ Exploitability Tests**
- [ ] **Can a liquidator repeatedly perform small liquidations to avoid full liquidation?**
- [ ] **Can a liquidator bypass the negative margin check by closing only 99.99% of a position?**
- [ ] **Does the contract enforce a minimum close ratio for liquidation to prevent abuse?**
- [ ] **Can an attacker intentionally manipulate a vault’s margin to make it appear safe while keeping a hidden bad debt?**
- [ ] **Are there any slippage tolerance checks that could be abused by liquidators?**

---

### **🚀 5️⃣ Mitigation and Fixes**
- [ ] **Implement a proportional bad debt payment requirement for partial liquidations.**
- [ ] **Prevent partial liquidations from leaving a position smaller than a reasonable threshold (e.g., 5% of original size).**
- [ ] **Introduce an insurance fund to cover bad debt when liquidators fail to absorb it.**
- [ ] **Enforce a liquidation cooldown to prevent liquidators from repeatedly avoiding bad debt responsibility.**
- [ ] **Ensure that undercollateralized positions are flagged for immediate full liquidation.**
- [ ] **Audit how margin is recalculated after each liquidation and verify it correctly accounts for partial liquidations.**

---

### **🛡️ Final Takeaway**
📌 **Why This Matters?**  
- Partial liquidations **must cover a fair share of bad debt** to prevent financial loss.  
- Liquidators **must not be able to game the system** by strategically liquidating only parts of positions.  
- Ensuring **robust bad debt handling** protects the protocol from long-term insolvency.  

📌 **Next Steps:**  
- Run **unit tests** to simulate partial liquidations.  
- Analyze **historical liquidation events** in deployed contracts to identify weaknesses.  
- Consider **adding logging or analytics** to monitor liquidator behavior over time.  

