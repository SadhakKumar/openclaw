# Betting Orchestration Skill (Parent)

Orchestrates 3-stage betting workflow via subagent chain.

## Workflow

### Stage 1: Balance Check 📊
```bash
Spawn subagent → runs balance-checker skill
Output: Current USDC/ETH wallet balance
```

### Stage 2: Project Analysis 🎯  
```bash
Spawn subagent (input: balance from #1)
→ runs project-analyze skill
Output: Recommended bet amount based on project quality + balance
```

### Stage 3: Execute Bet 💰
```bash
Spawn subagent (input: bet amount from #2)
→ runs execute_bet skill
Output: Transaction hash, approval TX, success status
```

### Final Report ✅/❌
After all 3 subagents complete:
- **All succeed** → `"Success! All bets executed successfully."`
- **Any fails** → `"Error: <details about which stage failed + retry suggestion>"`

---

## Commands

- **"Run betting pipeline"** → Full 3-stage workflow  
- **"Betting chain"** → Short form for full workflow  
- **"Stage 1/2/3 only"** → Run specific subagent(s)  
- **"Dry run"** → Execute without placing real bets  

---

## Error Handling

Gracefully handles failures at each stage:
- **Balance fetch fail** → Report "Unable to retrieve balance, check wallet/network"
- **Project analysis fail** → Report "Could not fetch projects, verify JSONBin access"
- **Bet execution fail** → Report "Bet failed at amount X, reason: <error>"

---

**Subagent Chain:**
1. `balance-checker` (wallet)
2. `project-analyze` (with balance input)
3. `execute_bet` (with recommended amount)
