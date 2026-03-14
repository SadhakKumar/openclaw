# Balance Checker Skill

Checks current wallet USDC/Eth balance before executing betting transactions or project analysis.

## Workflow

### 1️⃣ Fetch Balance
```bash
cd ~/scripts/src && node src/runGetBalance.js
```

This script will:
- Connect to blockchain RPC endpoint (Sepolia/Base)
- Query wallet balance for ETH and USDC
- Return formatted output with current holdings

### 2️⃣ Store State
Cache current balance in memory or temporary file:
```json
{
  "eth": "5.432",
  "usdc": "420.15",
  "checkedAt": "2026-03-14T11:48:00Z"
}
```

### 3️⃣ Use in Decisions
Balance feeds into:
- **Bet sizing** - Don't exceed 10-20% per wager
- **Project selection** - Higher balances enable larger bets on top picks
- **Portfolio diversification** - Spread across multiple projects if balance permits

---

## Commands

- **"Check balance"** → Fetch and display current holdings  
- **"Balance now"** → Quick status check  
- **"Balance <threshold>"** → Alert if below X USDC/ETH  
- **"Ready for analysis"** → Check before project review  

---

**Script:** `~/scripts/src/runGetBalance.js`  
**Command:** `node src/runGetBalance.js`  
**Current Balance (user-provided):** 5 USDC  
**Betting Limits:** Max 20% per bet recommended  
