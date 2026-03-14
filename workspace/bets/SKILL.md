# Betting Transaction Skill

Handle on-chain betting transactions using `run-bet.js`.

## Workflow

When requested to make a bet:

1. **Extract amount** from user message:
   - Look for `--amount=<VALUE>` or any number specified in the prompt (e.g., "5 ETH", "3 tokens")
   - If not mentioned, default to `1`

2. **Execute command**:
   ```bash
   cd ~/scripts/src && npm run bet -- --amount=<extracted_or_default>
   ```

3. **Capture output** and report back the transaction result

## Example Responses

- **"Place a bet of 5 tokens"** → `npm run bet -- --amount=5`
- **"Bet now"** (no amount) → `npm run bet -- --amount=1`
- **"Betting script"** → Run the command with default amount

---

**Tool path:** `bets` (skills directory in workspace)  
**Script location:** `~/scripts/src/run-bet.js`  
**Default bet:** `1` (unit unspecified)
