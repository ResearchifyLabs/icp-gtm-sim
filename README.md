# icp-gtm-sim

An agent skill that finds your **ICP** and validates your **GTM messaging** by testing copy
against hundreds of simulated buyer personas.

Paste a landing page, cold email, launch post or pitch. The skill builds a factorial audience
(role × company size × industry × revenue × geography…), has every persona react to the exact
copy, and tells you:

- **Who it lands with** — the specific conjunction (e.g. *growth leads at 11–50-person B2B
  SaaS companies under $1M revenue*), specific enough to build a list against.
- **What's holding it back** — separated into *wrong audience* (fix the targeting) and
  *wrong message* (fix the copy or proof).
- **What to do next** — one real-world check and one message variant worth testing.

## How it works

1. **Take the brief.** Your exact copy — plus a quick check for things that skew results
   (copy that names its own audience, a missing price, the channel).
2. **Propose the audience.** 4–5 filterable factors, every valid combination once,
   impossible companies dropped (a 5-person company with $100M revenue isn't a segment).
   You edit it in plain language: "drop manufacturing", "add funding stage", "only US".
3. **Run it.** Each persona scores relevance, clarity and trust on a 1.00–5.00 scale and picks
   an intent: ignore · reject · inspect details · self-serve trial · bring to team. Large runs
   are split into parallel batches.
4. **Check before analysing.** Flags flat dimensions, stereotyped responses and batch noise
   before any segment claim is made.
5. **Report.** A short answer, a segment table with *n* on every number, and the full CSV as
   an audit trail.

It can also compare two runs — two message variants, a re-test after a copy change, or results
from another tool.

## Install

**Any agent** — Claude Code, Codex, Cursor, GitHub Copilot and 75+ others, via
[skills.sh](https://skills.sh):

```bash
npx skills add ResearchifyLabs/icp-gtm-sim
```

**Claude Code plugin** — inside Claude Code:

```
/plugin marketplace add ResearchifyLabs/icp-gtm-sim
/plugin install icp-gtm-sim@researchify-labs
```

**Manually** — the skill is a single [`SKILL.md`](SKILL.md) file. Clone the repo into your
agent's skills folder, e.g. for Claude Code:

```bash
git clone https://github.com/ResearchifyLabs/icp-gtm-sim ~/.claude/skills/icp-gtm-sim
```

**Agents without skill support** — add `SKILL.md` to the agent's context or instructions and
ask it to follow the skill.

## Use

Ask in plain language:

> Use icp-gtm-sim to test this message: *"…your copy…"*

or just *"who is this for?"*, *"will this land?"*, *"test this landing page"*. In Claude
Code you can also run it directly: `/icp-gtm-sim` when installed as a skill, or
`/icp-gtm-sim:icp-gtm-sim` when installed as a plugin.

Works best in an agent that can run code (to build the persona grid and compute segment
averages) and spawn subagents (to run batches in parallel).

## A note on what this is

These are model predictions about attribute labels, not real customers. The output is a
sharper hypothesis and a shorter list of things to test with real people — not a substitute
for them.

## Hosted version

This skill is open source and free. For frequent use, [tesemble.com](https://tesemble.com)
runs it with more accurate, cheaper and faster results.

## License

[MIT](LICENSE) © Researchify Labs
