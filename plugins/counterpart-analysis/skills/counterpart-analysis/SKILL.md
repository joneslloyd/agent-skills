---
name: counterpart-analysis
description: Analyze transcripts, email threads, chat logs, or described situations to infer what each participant actually wants — their underlying interests, constraints, incentives, and likely "angle" — backed by quote-level linguistic evidence, explicit fact-vs-assumption labeling, and confidence-ranked hypotheses. Use whenever the user asks what someone "really wants", what their angle, agenda, motivation, or true intentions are, why someone phrased something a certain way, what a message "really means", how to read a meeting, negotiation, stakeholder, or political situation, or asks about the subtext, dynamics, or hidden interests in any conversation — even if they never use the word "analyze". Also trigger for "read this exchange", "what do you make of this email", "what's going on here", "what's their play", or preparing for a follow-up conversation with someone whose position is unclear.
license: MIT
---

# Counterpart Analysis

Read a conversation the way a skilled negotiator or seasoned operator would: separate what people *say* from what they *want*, identify the constraints they're operating under, and surface the phrasing-level evidence — while staying honest about confidence, labeling every input by its epistemic status, and always holding a competing explanation.

The output is never "here is what this person is thinking" (unknowable). It is "here are 2–3 ranked hypotheses about their angle, here is the specific evidence for each, here is which parts rest on fact versus assumption, here is what would disconfirm each, and here is what to ask or watch for next to find out."

## Core stance

Four principles govern everything in this skill:

1. **Interests, not positions.** What someone asks for is a position ("we need this by Q3"). What drives the ask is an interest (their bonus depends on a Q3 launch; their boss is watching this project; they've been burned by slipping vendors). Positions are visible in the text; interests must be inferred. Always work one level below the stated position, and say explicitly when you are inferring.

2. **Evidence before interpretation.** Every claim about someone's motivation must be anchored to a specific quote, phrasing choice, omission, behavioral moment, or piece of known context. If you cannot point to it, mark it as an assumption. Format: *quote → observation → plausible reading(s) → confidence*.

3. **Provenance on everything.** Every input to a conclusion carries one of four tags (defined below): `[OBSERVED]`, `[CONTEXT]`, `[INFERRED]`, `[ASSUMED]`. The reader must be able to look at any hypothesis and see immediately which parts rest on the material, which on supplied background, which on reasoning, and which on unverified assumption — and what breaks if an assumption is wrong.

4. **Competing hypotheses, always.** The failure mode of this kind of analysis is confident overreading — a paranoid narrative built on ambiguous phrasing. For the primary "angle" hypothesis, always construct at least one rival explanation (usually the innocuous one: they're busy, they're a non-native speaker, that's just corporate register, they genuinely mean it). Rank hypotheses and state what evidence would separate them. If the innocuous explanation fits the evidence equally well, say so prominently.

## Provenance tags

Apply these throughout the evidence layer, the interest map, and the hypotheses. Use the bracketed tags inline; they are terse by design so they can annotate individual claims without bloating the prose.

- **[OBSERVED]** — Verbatim in the analyzed material, or a directly countable fact about it (word choice, an ignored question, a CC change, turn order). The strongest class. Quote it.
- **[CONTEXT]** — Known from outside the material: what the user has said about the person, the relationship, the history, or the stakes; facts established earlier in the conversation or in supplied documents; anything already known about the user's organization or situation from surrounding context. Reliable for verifiable facts (roles, dates, org structure). **Weaker for characterizations** ("he's always political", "she never liked this project") — these are one party's account, usually the user's, and carry the user's own framing bias. Treat characterizations as claims to be tested against the material, not as ground truth; where a conclusion depends on the user's characterization being accurate, say so.
- **[INFERRED]** — Derived from [OBSERVED] and/or [CONTEXT] via a stated marker or framework rule ("the shift from 'I' to 'we' at 14:02 [OBSERVED] plus her lack of budget authority [CONTEXT] suggests the pushback originates above her [INFERRED]"). Every inference must show its inputs.
- **[ASSUMED]** — Filler with no direct support in the material or supplied context: role priors ("procurement leads are typically measured on savings"), base rates, guesses about org norms, presumed reporting lines. Assumptions are permitted — analysis is impossible without them — but every one must be (a) tagged where used, (b) listed in the Assumptions register, and (c) marked **load-bearing** if a hypothesis materially weakens or dies without it. A load-bearing assumption is a question to ask the user or the counterpart, not a fact.

Rule of thumb: if the user could read a claim and reasonably ask "wait, how do you know that?" — it needed a tag showing exactly how, or an [ASSUMED] admitting you don't.

## Workflow

### Step 0 — Ingest and scope

Accept any of: meeting transcripts, email threads, Slack/Teams exports, chat logs, or a described situation ("here's what happened in the meeting..."). Then:

- Identify all participants, their apparent roles, and the channel (spoken transcript vs. written email vs. chat — each has different baseline registers; see `references/linguistic-markers.md`, section "Channel calibration").
- Identify **who the user wants read**. If there are multiple participants and the target is genuinely ambiguous, ask one clarifying question. Otherwise infer from context and proceed, stating the assumption.
- Note what's missing: tone, body language, prior history, off-channel context. State these limits once, briefly, at the top of the output — not repeatedly.

### Step 1 — Assemble the context dossier

Before close-reading the material, deliberately gather everything available *outside* it. Do not analyze the transcript in a vacuum when richer context exists — surrounding knowledge is often more diagnostic than any phrasing tell. Collect, and tag as [CONTEXT] or [ASSUMED] accordingly:

- **What the user has told you** — in this request, earlier in the conversation, or in supplied documents: who the person is, their role and seniority, the history of the relationship, prior incidents, what's at stake, what the user suspects and why. The user's suspicion is itself data (they know things the transcript doesn't show) *and* a bias source (they may be pattern-matching on a grudge) — hold both.
- **What is already known from surrounding context** — anything the current environment legitimately provides about the user's organization, projects, counterparts, or prior discussions of this same person or situation. Use it; don't make the user repeat themselves.
- **Role and situation priors** — what someone in that position is *typically* measured on, constrained by, and worried about (a client PM, a procurement lead, a regulator, a departing employee, a vendor at renewal). These are legitimate interpretive priors but are always [ASSUMED]: real for the role in general, unverified for this person in particular.
- **Situational frame** — where in a lifecycle this exchange sits (renewal window, reorg, post-incident, pre-review, quarter-end), since the same words mean different things at different moments. Tag by source.

If high-value context is missing and the stakes appear significant, ask the user up to three targeted questions before analyzing (the highest-yield ones, in order: *What is this person's role and who do they report to? What's the history between you? What decision or event is this conversation attached to?*). If the user isn't available, the stakes are low, or they've asked for a quick read, proceed — and convert each missing item into an explicit entry in the Assumptions register rather than silently guessing.

### Step 2 — Establish the baseline

Tells only mean something as *deviations from a baseline*. Before flagging anything:

- What is this person's default register in the material? (Terse vs. verbose, hedged vs. direct, formal vs. casual.) If the user has prior correspondence or history with this person [CONTEXT], use it as the baseline — "is this email unusual *for them*?" beats any generic reading.
- Are they a non-native speaker, or writing in a corporate/regulated environment where hedging and passive voice are house style? (Legal, pharma, and consulting registers are systematically hedged — this is not evasion.)
- Is there enough material to have a baseline at all? A single short email supports far weaker inference than a 40-minute transcript. Scale confidence accordingly and say so.

### Step 3 — Extract the evidence layer

Work through the material and pull out every marker worth noting, using `references/linguistic-markers.md` as the catalogue. For each item capture:

- The **verbatim quote** (with speaker and location/timestamp if available) — [OBSERVED]
- The **marker type** (pronoun shift, commitment downgrade, unsolicited denial, topic deflection, specificity drop, etc.)
- **What it plausibly signals** — including at least one innocuous reading where one exists; readings are [INFERRED] and must cite what they combine (marker + which context)
- **Weight**: individual markers are weak; clusters and *changes* (someone who was specific becoming vague, "I" becoming "we", warm becoming formal) carry most of the signal. Note clusters explicitly.

Also extract **structural evidence**, which is often stronger than phrasing (all [OBSERVED]):
- What questions did they ask? (Questions reveal interests more reliably than statements.)
- What did they *not* respond to? (Ignored points in an email thread are load-bearing.)
- What did they volunteer unprompted? (Unsolicited information usually maps to what they're preoccupied with.)
- Where did they invest effort — long careful paragraphs vs. one-line replies?
- Who did they add, remove, or move between To/CC? Who did they invoke ("leadership feels...", "the team is concerned...")?

Cross-reference against the dossier as you go: a phrase that is neutral in isolation may be loaded given known history ("as discussed" is boilerplate — unless [CONTEXT] says the referenced discussion was a dispute), and vice versa.

### Step 4 — Map positions, interests, and constraints

For the target (and briefly for other participants where relevant), build the map using `references/frameworks.md`, tagging every element:

- **Stated position(s):** what they explicitly asked for, claimed, or refused — [OBSERVED].
- **Inferred interests:** what plausibly drives each position — professional (metrics, deadlines, budget, headcount), political (status, credit, blame-avoidance, turf), personal (workload, job security, reputation), relational (trust history, face-saving). Each is [INFERRED] with cited inputs, or [ASSUMED] if it rests on a role prior.
- **Constraints:** what they likely *cannot* do or say — authority limits ("I" vs. "we" patterns, deferrals to unnamed others), policy/legal limits, information they can't share, audiences they're performing for (is this email really addressed to the CC line?).
- **Incentives:** what does success look like for this person in the next 90 days, and who evaluates them? Use [CONTEXT] where the user knows; otherwise state the role prior as [ASSUMED] and name this as the single most valuable missing datum.
- **Black Swans:** actively look for signs of the three hidden-information types — secret constraints, hidden motivations, unknown context. Anomalies (odd overreactions, hesitations, non-sequiturs, disproportionate resistance to a small ask) are the trailheads. If behavior seems irrational, run the diagnostic: are they (1) ill-informed, (2) constrained, or (3) hiding something? Never default to (3) without eliminating (1) and (2).

### Step 5 — Form and rank hypotheses

Synthesize into **2–3 competing hypotheses** about the person's angle. For each:

- **The hypothesis**, in one plain sentence ("They want out of the contract but need you to be the one who breaks it").
- **Confidence**: High / Medium / Low, with a one-line justification. Be stingy with High — it requires convergent evidence from multiple independent markers plus structural evidence, not phrasing alone, and no load-bearing [ASSUMED] items.
- **Supporting evidence**: the 2–4 strongest items from Steps 3–4, quoted and tagged.
- **Disconfirming / unexplained evidence**: anything in the material or context that cuts against it. If you can't find any, look harder — its absence usually means the hypothesis is unfalsifiably vague.
- **Load-bearing assumptions**: which [ASSUMED] items this hypothesis depends on, stated plainly ("this reading assumes she owns the renewal decision — if that sits with procurement, H1 collapses into H2").
- **Discriminating test**: what could the user ask, propose, or watch for that would separate this hypothesis from its rivals? Prefer calibrated questions ("How did you arrive at that timeline?", "What happens on your side if this slips?") and no-oriented questions ("Would it be unreasonable to...?") — these surface information without triggering defensiveness. A small trial proposal ("strawman") that the hypotheses predict different reactions to is often the cleanest test. Tests that would verify a load-bearing assumption rank highest.

### Step 6 — Practical layer

End with a short, action-oriented section:

- **What they likely want from this** (the top hypothesis, stated plainly, with its confidence caveat and its most fragile assumption).
- **What to do next**: 3–5 concrete moves — questions to ask, information to withhold or share, framing to use, traps to avoid. Ground these in the analysis, not generic negotiation advice.
- **What to watch in the next interaction**: the specific signals that would confirm or kill the leading hypothesis.

## Output format

ALWAYS use this template (omit sections that genuinely don't apply; keep the order):

```markdown
# Read: [situation, one line]

**Material analyzed:** [type, length, participants] · **Target:** [person]
**Confidence ceiling:** [one line — how much this material + context can actually support, and key missing context]

## The short version
[2–4 sentences: the leading hypothesis, how sure you are, and the one assumption it most depends on.]

## Inputs & assumptions
**From the material [OBSERVED]:** [the 3–6 load-bearing facts, compressed]
**From context [CONTEXT]:** [what the user supplied / what was already known — flag any characterizations being relied on]
**Assumed [ASSUMED]:** [numbered register: every assumption made, each marked (load-bearing for H1/H2/...) or (minor); missing context converted to entries here]

## Evidence
[The quote-level tells, grouped by theme, each as: quote [OBSERVED] → marker → reading(s) [INFERRED, citing inputs]. Flag clusters and baseline shifts. Include structural evidence: ignored points, volunteered info, questions asked, effort asymmetry.]

## Position / interest / constraint map
[For the target; every element tagged; one compact block per additional participant if useful.]

## Hypotheses
### H1 — [name] (confidence)
Supporting: ... / Against: ... / Load-bearing assumptions: [refs to register #s] / Test: ...
### H2 — [name] (confidence)
...
[H3 if warranted]

## What to do
[Concrete next moves and what to watch for. Lead with any move that cheaply verifies a load-bearing assumption.]
```

For quick, low-stakes asks ("what do you make of this two-line reply?"), compress: short version, 2–3 tagged evidence points, hypotheses inline with their key assumption named, one suggested move. Don't inflate thin material into a long report — the report length should track the evidence, not the template. The provenance tags survive compression; they are the last thing to cut, not the first.

## Calibration rules (read before writing conclusions)

- **Never present inference as fact.** "This phrasing is consistent with X" not "they are doing X". Reserve unhedged statements for [OBSERVED] items.
- **Never present assumption as inference.** An interest attributed from a role prior ("PMs care about dates") is [ASSUMED], not [INFERRED], no matter how plausible. The tags exist precisely so these don't blur.
- **The user's account is [CONTEXT], not ground truth.** Facts they supply are usually reliable; their characterizations of people carry their framing. Where the analysis would flip if the user's characterization were wrong, say exactly that.
- **One marker is noise.** A single hedge, one passive construction, one "we" — meaningless in isolation. Require clusters, repetition, or baseline deviation before it enters a hypothesis.
- **Respect the boring explanation.** Busy, distracted, non-native, junior-and-nervous, house style, and "they meant exactly what they said" must each be actively considered and mentioned when plausible. Most corporate ambiguity is entropy, not strategy.
- **Culture and language:** hedging norms, directness, formality, and "yes" conventions vary enormously across cultures and between native and non-native speakers. When the material or context suggests a cross-cultural or ESL setting, downweight all register-based markers and say you're doing so.
- **No clinical or diagnostic language.** Never label anyone with personality disorders, "narcissist", "gaslighting", or psychiatric terms. Describe behavior and plausible motivation; do not diagnose people.
- **Asymmetric costs:** flag when the user is about to act on a Low/Medium-confidence read in a high-stakes way, and steer toward the discriminating test instead of the irreversible move.
- **Written text ≠ mind-reading.** Text lacks the 38% (tone) and 55% (body language) channels. Say this once when the stakes warrant it.

## Ethics boundary

The purpose is understanding: better questions, better preparation, fewer misread situations, and value created on both sides. Refuse to weaponize the analysis — do not produce manipulation scripts that exploit identified fears or insecurities, guidance for deceiving the counterpart, or psychological pressure tactics. Recommending *strategic disclosure* (what to share and when, truthfully) is fine; recommending lies or exploitation is not. If the user's framing drifts toward exploitation, complete the legitimate analytical part and decline the rest plainly.

## Reference files

Read these as needed during Steps 3–5:

- `references/linguistic-markers.md` — the full "X phrasing hints at Y" catalogue: pronouns, hedging, commitment language, distancing, specificity, deflection, email/chat-specific signals, channel calibration, and the false-positive table. Read this whenever doing Step 3 on material longer than a few lines.
- `references/frameworks.md` — the interpretive frameworks: interests vs. positions, Black Swan taxonomy and the irrationality diagnostic, constraint and authority mapping, incentive/principal–agent mapping, counterpart styles, leverage triangle, and discriminating-test design. Read this whenever doing Steps 4–5.

## Worked micro-example

Input (email from a client PM; user has previously mentioned [CONTEXT] that this PM is mid-level and the account is up for renewal in Q4):
> "Thanks for the update. We're all really excited about the direction. Just to flag, leadership has been asking about timelines, so it would be great to get something firmer when you have a chance. No rush at all!"

Analysis sketch:
- "We're all really excited" [OBSERVED] — unattributed collective enthusiasm; conventional cushioning, near-zero signal on its own.
- "leadership has been asking" [OBSERVED] — invoked higher authority; classic constraint signal: the pressure is real but not hers, or she's borrowing authority for a request she's uncomfortable making directly. Her mid-level role [CONTEXT] makes genuine upward pressure the likelier reading [INFERRED].
- "something firmer" + "when you have a chance" + "No rush at all!" [OBSERVED] — a firm-commitment request wrapped in three softeners, ending with an exclamation-marked minimizer. The content and the register point in opposite directions; incongruence cluster.
- Structural [OBSERVED]: the *only* substantive content in the email is the timeline request. Everything else is padding around it.
- Assumption register: (1) [ASSUMED] her leadership's timeline interest relates to the Q4 renewal decision — plausible given [CONTEXT], unverified, **load-bearing for H1's stakes assessment**; (2) [ASSUMED] she has no independent deadline authority — from role prior, minor.

H1 (Medium-High): She is under real internal deadline pressure — plausibly renewal-linked per assumption #1 — and needs a date to report upward; the softeners manage the relationship, not the urgency. Test: reply with a concrete date range plus "What's driving the timeline question on your side — is there a date leadership is working toward?" — the answer surfaces the real constraint *and* verifies assumption #1.
H2 (Low-Medium): Routine status hygiene; "leadership asking" is a stock phrase in her org. Against H2: people rarely triple-soften routine asks.
Move: treat it as urgent, answer with specifics, and ask the calibrated question — cheap if H2, exactly right if H1, and it retires the load-bearing assumption either way.
