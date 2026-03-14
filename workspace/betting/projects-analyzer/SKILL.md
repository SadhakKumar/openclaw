# Project Analyzer Skill

Fetches projects from JSONBin using `getJsonbin.js` and analyzes project descriptions for betting recommendations.

## Workflow

### 1️⃣ Fetch Projects
```bash
cd ~/scripts/src && npm run get-jsonbin
```

This script will:
- Connect to your JSONBin endpoint securely
- Authenticate using stored credentials
- Return full project details with descriptions, team info, and metadata

### 2️⃣ Analyze Descriptions
Read all returned projects and evaluate based on:
- **Innovation** - AI/ML features, unique value propositions
- **Market Need** - Clear problem/solution fit
- **Scalability** - Potential for growth and adoption
- **Team Credibility** - HackathonId context, project maturity

### 3️⃣ Recommend Bet Amount
Calculate optimal bet based on:
- **Your balance**: Currently 4 USDC (update when it changes)
- **Project score**: Top picks get priority bets (0.5-2 USDC range)
- **Risk assessment**: Diversified vs concentrated strategy

### 4️⃣ Execute Bet
Use betting skill to place recommended wager:
```bash
npm run bet -- --amount=<recommended_amount>
```

---

## Commands

- **"Analyze projects"** → Fetch and evaluate all projects  
- **"Top picks"** → Show highest-rated projects with reasoning  
- **"Bet on best"** → Execute bet on top recommendation  
- **"Balance <X>"** → Update balance before analysis  

---

**Script Location:** `~/scripts/src/getJsonbin.js`  
**Command:** `npm run get-jsonbin`  
**JSONBin Endpoint:** `https://api.jsonbin.io/v3/b/69b5223fb7ec241ddc6950cd/latest`  
**Betting Default:** Up to 4 USDC total allocation  
