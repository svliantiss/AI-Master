# 💻 Verified CLI Commands & Patterns

## ✅ GOOD: Pre-Approved & Token-Efficient
*Agent: You may run these commands confidently without asking, adjusting variables as needed.*

**Generate Multiple Test Keys (Simple Loop + cURL + jq):**
```bash
for i in {1..6}; do curl -s -X POST http://localhost:9999/keys -H "X-Passy-API-Key: mvkXpIZqPnQqX7ALo9JhbWA6DFGZYOdB" -H "Content-Type: application/json" -d '{"isTest": true}' | jq -r '.key.token'; done
```

**Type Checking (No Build Output):**
```bash
bun run tsc --noEmit
```

**Check Git Status (Short Format):**
```bash
git status -s
```

---

## ❌ BAD: Forbidden & Brittle
*Agent: NEVER use these commands.*

- **Truncating Output:** `head -n 50 file.ts` or `tail -n 20 file.ts` *(Forbidden: You will lose crucial context. Use your native Read tool instead).*
- **Complex Bash Scripts:** Writing multi-line bash scripts with heavy piping to parse data. *(Forbidden: Waste of tokens. Make an API route or use a simple one-liner).*
- **File Editing via CLI:** `sed -i '' 's/foo/bar/g' file.ts` *(Forbidden: Corrupts files easily. Rewrite the file or use an AST tool).*
