---
name: last30days
version: "3.3.2"
description: "Research what people actually say about any topic in the last 30 days. Pulls posts and engagement from Reddit, X, YouTube, TikTok, Hacker News, Polymarket, GitHub, and the web (via Kagi), then returns ranked, sourced evidence."
argument-hint: 'last30days nvidia earnings reaction | last30days AI video tools'
allowed-tools: Bash, Read
user-invocable: true
metadata:
  openclaw:
    emoji: "📰"
---

# last30days — recent multi-source research (slim)

A Python engine does all the data work: it queries Reddit, X, Hacker News, the web
(via Kagi), YouTube, Polymarket and more, ranks results by engagement, and prints ranked
evidence with sources. **Your only job is to run it and summarize what it found — do not
search the web yourself.**

## Run it

1. Set `SKILL_DIR` to the directory that contains THIS SKILL.md (the path you just read it from).
2. Run exactly this, replacing TOPIC:

   ```bash
   python3 "${SKILL_DIR}/scripts/last30days.py" "TOPIC" --emit md --quick
   ```

   - Web search is **Kagi, already configured as the default** — do NOT pass `--web-backend`.
   - Drop `--quick` for a deeper, slower pass.

3. Read the **Ranked Evidence Clusters** the engine prints, then write a short brief: a few
   plain paragraphs on the main themes people are discussing, grounded ONLY in that evidence
   (link a source where useful). End with the engine's `✅ All agents reported back!` footer verbatim.

## Do NOT

- Do NOT use `curl`, `WebSearch`, or any manual search — the engine handles every source.
- Do NOT guess or discover install paths, and do NOT write a path-discovery loop — use `SKILL_DIR` exactly as above.
- Do NOT generate a query plan — the engine plans on its own when `--plan` is omitted.
- Do NOT invent facts beyond the engine's evidence, and do NOT append your own "Sources:" list.

If the engine prints an error, report it plainly — do not fall back to your own search method.

> The full, frontier-model version of this skill (synthesis LAWs, voice contract, planning
> steps) is preserved alongside as `SKILL.full.md`. Swap it back in if you run this on a
> stronger model and want the polished output contract.
