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
---

## 🚀 Status
Codex is in **prototype stage** (Python CLI → JSON/HTML reports).  
The focus is on proving that *failure-only memory* works: lean, auditable, and useful.

---

## 🤝 Get Involved
- If your framework already produces reports like this → please share an example.  
- If not, and you want to test Codex on your agent loop → open an Issue or DM me.  
- Ideas, critiques, and forks welcome. The goal is simple:  
  **stop hoarding noise, remember what failed, and learn from it.**
