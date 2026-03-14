# Betting Transaction Skill

Execute on-chain betting transactions using `run-bet.js`.

## Usage

When prompted to place a bet:

1. **Extract amount** from user message:
   - Look for explicit amounts like `--amount=<value>`, "5 ETH", "10 tokens"
   - If no amount specified, default to `1`

2. **Run command**:
   ```bash
   cd ~/scripts/src && npm run bet -- --amount=<value>
   ```

3. **Report results** back to user with any transaction status/output

## Examples

- User: *"Place a bet of 5 tokens"* → `--amount=5`
- User: *"Betting script now"* → `--amount=1` (default)
- User: *"Bet 100 ETH"* → `--amount=100`

---

**Script:** `~/scripts/src/run-bet.js`  
**Command:** `npm run bet -- --amount=<value>`  
**Default:** `1`
