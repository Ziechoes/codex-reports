D# codex-reports
Lightweight module for agent memory. Logs only reasoning failures (contradictions, opacity gaps, unknowns) → compact, auditable Reasoning Reports.
---

## 📖 What is Codex?
Most agent frameworks store *everything* into memory.  
That creates:
- Memory bloat (vector DBs full of junk)  
- Agents repeating the same mistakes  
- No clear audit trail of why reasoning collapsed  

Codex flips this around.  
It only logs **failure points**:
- ❌ Contradictions  
- ⚠️ Opacity gaps  
- ❓ Unknowns  

This produces a **compact, auditable Reasoning Report** instead of a noisy transcript.

---

## 📝 Demo Output

Example collapse report for a trivial failure (`2+2=5`):

```json
{
  "collapse_point": "Arithmetic Error",
  "claim": "2+2=5",
  "evidence": "Contradicts elementary arithmetic",
  "status": "collapsed",
  "timestamp": "2025-08-29T11:24:00Z"
}
Reasoning Report
----------------
Collapse Point: Arithmetic Error
Claim: 2+2=5
Status: ❌ Collapsed
Notes: Contradiction detected against axiomatic arithmetic rules.
