# Agent Skills

A collection of agent skills. Skills follow the open [Agent Skills](https://agentskills.io) `SKILL.md` format and this repository doubles as a [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugin-marketplaces).

## Skills

### counterpart-analysis

Read transcripts, email threads, chat logs, or described situations to infer what each participant actually wants — their underlying interests, constraints, incentives, and likely "angle".

- **Quote-level evidence**: every motivational claim anchors to a verbatim quote, marker, or structural observation (ignored points, CC changes, effort asymmetry, questions asked).
- **Provenance tagging**: every input is labeled `[OBSERVED]` (in the material), `[CONTEXT]` (supplied background), `[INFERRED]` (derived, with cited inputs), or `[ASSUMED]` (unverified prior) — so you can see whether a conclusion rests on fact or assumption, and which assumptions are load-bearing.
- **Competing hypotheses**: 2–3 ranked hypotheses, each with supporting *and* disconfirming evidence, and a concrete discriminating test (calibrated question, no-oriented question, or strawman proposal) to run next.
- **Calibration guardrails**: baseline-first reading, a false-positive table of boring explanations that must be beaten, cross-cultural/ESL downweighting, and hard limits on confidence for thin material.
- **Ethics boundary**: analysis for understanding and preparation — not manipulation scripts.

Reference files: `references/linguistic-markers.md` (the "X phrasing hints at Y" catalogue, 16 sections) and `references/frameworks.md` (interests vs. positions, Black Swans, irrationality diagnostic, incentive mapping, counterpart styles, test design).

## Installation

### Claude Code (recommended)

```shell
/plugin marketplace add joneslloyd/agent-skills
/plugin install counterpart-analysis@agent-skills
```

Or from the terminal:

```bash
claude plugin marketplace add joneslloyd/agent-skills
claude plugin install counterpart-analysis@agent-skills
```

Update later with `/plugin update` (or `/plugin marketplace update agent-skills`).

### Manual (Claude Code, Codex, and other agentskills.io-compatible agents)

Copy the skill folder into your agent's skills directory:

```bash
git clone https://github.com/joneslloyd/agent-skills.git
cp -r agent-skills/plugins/counterpart-analysis/skills/counterpart-analysis ~/.claude/skills/
```

For a repo-local install, use `.claude/skills/` in your project instead of `~/.claude/skills/`.

### Claude.ai / Claude apps

Download the packaged `.skill` file from [Releases](../../releases) and upload it in a conversation — the file card shows a **Save skill** button (requires an org/plan that allows skill creation), or add it via Settings → Capabilities → Skills.

## Repository structure

```
.
├── .claude-plugin/
│   └── marketplace.json          # marketplace catalog
├── plugins/
│   └── counterpart-analysis/
│       ├── .claude-plugin/
│       │   └── plugin.json       # plugin manifest (bump version on release)
│       └── skills/
│           └── counterpart-analysis/
│               ├── SKILL.md
│               └── references/
│                   ├── linguistic-markers.md
│                   └── frameworks.md
├── LICENSE
└── README.md
```

## Releasing

1. Edit the skill under `plugins/counterpart-analysis/skills/counterpart-analysis/`.
2. Bump `version` in `plugins/counterpart-analysis/.claude-plugin/plugin.json` — users only receive updates when this string changes.
3. Validate: `claude plugin validate .`
4. Commit, push, and (optionally) attach a freshly packaged `.skill` file to a GitHub Release for claude.ai users.

## License

MIT — see [LICENSE](LICENSE).
